<template>
    <div class="product">
        <a
            class="web-product"
            :href="productData.href"
            target="_blank"
            rel="noopener"
        >
            <img
                class="web-product__img"
                :src="productData.img"
                :alt="`${productData.name}-logo`"
            />
            <div class="web-product__header">
                <span> {{ productData.name }} </span>
                <span> {{ productData.desc }} </span>
            </div>
            <img
                :class="productData.pwa ? 'pwa-logo' : 'pwa-logo gray-scale'"
                src="../assets/images/PWA.png"
                alt="pwa-logo"
            />
        </a>
    </div>
</template>

<script>
export default {
    name: 'Product',
    props: {
        productData: {
            type: Object,
        },
    },
}
</script>

<style lang="sass" scoped>
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
        filter: drop-shadow(2px 2px 5px #694BA6)
    .web-product
        width: 100%
        display: flex
        align-items: center
        justify-content: space-between
        text-decoration: none
        padding: .3em 1.3em
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
            width: calc( 100% - calc( 1.3em + 80px ) )
            > span // 1.Product Title - 2.Product Description
                margin: 0 10px
                &:first-child
                    font-weight: 800
        .pwa-logo
            height: 10px
            object-fit: cover
        .gray-scale
            filter: grayscale(100%)
            opacity: .5
@media screen and (max-width: 750px)
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
