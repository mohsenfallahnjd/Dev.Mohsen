<template>
    <div class="link">
        <div v-for="(product, i) in products" :key="i" class="product">
            <a
                class="web-product"
                :href="product.href"
                target="_blank"
                rel="noopener"
            >
                <img
                    class="web-product__img"
                    :src="product.img"
                    :alt="`${product.name}-logo`"
                />
                <div class="web-product__header">
                    <span> {{ product.name }} </span>
                    <span> {{ product.desc }} </span>
                </div>
                <img
                    :class="product.pwa ? '' : 'gray-scale'"
                    id="pwa-logo"
                    src="../assets/images/PWA.png"
                    alt="pwa-logo"
                />
            </a>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Link',
    data: () => ({
        products: [
            {
                name: 'Coronavirus Tracker',
                img: require('../assets/images/webLogo/covid.svg'),
                desc: 'The Progressive Coronavirus Tracker',
                href: 'https://covid.mohsenfallah.ir/',
                pwa: true,
            },
            {
                name: 'LiaraPWA',
                img: require('../assets/images/webLogo/liara.svg'),
                desc: 'PWA for manage own Liara.ir panel',
                href: 'https://liara.mohsenfallah.ir/',
                pwa: true,
            },
            {
                name: 'Todo List',
                img: require('../assets/images/webLogo/vue-js.svg'),
                desc: 'The Loginable TodoList',
                href: 'https://todo.mohsenfallah.ir/',
                pwa: false,
            },
        ],
    }),
}
</script>

<style lang="sass" scoped>
.link
    .product
        width: 100%
        height: 50px
        border-radius: 8px
        box-shadow: 3px 3px 8px 0px rgba(0,0,0,0.3)
        display: flex
        align-items: center
        justify-content: center
        margin: 15px 0px
        &:hover
            filter: drop-shadow(2px 2px 3px #694BA6)
        .web-product
            width: 100%
            display: flex
            align-items: center
            justify-content: space-between
            text-decoration: none
            padding: .8em 1.3em
            color: #000
            &:focus
                outline: none
            &__img
                width: auto !important
                height: 30px
                object-fit: cover
            &__header
                display: flex
                align-items: center
                justify-content: center
                width: calc( 100% - calc( 1em + 80px ) )
                > span
                    margin: 0 10px
                    &:first-child
                        font-weight: 800
            #pwa-logo
                height: 10px
                object-fit: cover
            .gray-scale
                filter: grayscale(100%)
                opacity: .5
    @media screen and (max-width: 700px)
        .product
            height: 60px
        .web-product
            &__header
                flex-direction: column
                font-size: 12px
                > span
                    &:first-child
                        font-size: 16px
</style>
