<template>
    <div class="home">
        <div id="copy-notif">username copy to your clipboard!</div>

        <img class="home__avatar" :src="mohsen.avatar" alt="mohsen-avatar" />

        <h1 class="home__name">{{ mohsen.name }}</h1>

        <h3 class="home__job-title">
            Front-end,
            <a
                id="vue-word"
                class="link"
                href="https://vuejs.org/"
                target="_blank"
                rel="noopener"
            >
                Vue.js
                <img id="vuejs-logo" :src="mohsen.vueLogo" alt="vuejs-logo" />
            </a>
            | Public Relations Manager at
            <a
                class="link"
                id="lahzino"
                href="https://lahzino.ir/"
                target="_blank"
                rel="noopener"
            >
                Lahzino.ir
            </a>
        </h3>

        <p class="home__description">
            in rel with
            <a
                id="pwa-address"
                href="https://web.dev/progressive-web-apps/"
                target="_blank"
                rel="noopener"
            >
                <img
                    id="pwa-address__logo"
                    :src="mohsen.pwaLogo"
                    alt="pwa-logo"
                />
            </a>
            <br />
            I'm on all Social Medias<br />with:
            <span id="username" @click="copyUsername">
                {{ mohsen.username }}
            </span>
        </p>
        <div id="socials-comp"><Socials :socialsData="socials" /></div>
        <h3 class="products-list-title">--- Products List ---</h3>
        <div id="product-comp">
            <Product
                v-for="(product, i) in productsList"
                :key="i"
                :productData="product"
            />
        </div>
    </div>
</template>

<script>
import Socials from '@/components/Socials.vue'
import Product from '@/components/Product.vue'
import { productsList } from '../data'
import { mohsen } from '../data'
import { socials } from '../data'
export default {
    name: 'Home',
    components: {
        Socials,
        Product,
    },
    data: () => ({
        mohsen,
        productsList,
        socials,
    }),
    methods: {
        copyUsername() {
            navigator.clipboard.writeText(this.mohsen.username)
            const notif = document.getElementById('copy-notif')
            notif.style.top = '0px'
            setTimeout(() => {
                notif.style.top = '-61px'
            }, 3000)
        },
    },
}
</script>

<style lang="sass" scoped>
$bgColor: #fafafa
$lahzino: #073b9d
$description: #566573
$vueColor: #41B883
$vueColor_2: #265942
$avatarBorder: #E8E8E8

.home
  width: 100%
  height: 100%
  overflow: hidden auto
  background-color: $bgColor
  display: flex
  flex-direction: column
  justify-content: center
  align-items: center
  padding: 3em 0
  #copy-notif
    width: 30%
    height: 40px
    position: absolute
    top: -61px
    background-color: $vueColor_2
    color: #fafafa
    transition: top .3s ease
    display: flex
    align-items: center
    justify-content: center
    font-size: 20px
    border-radius: 0 0 8px 8px
  &__avatar
    width: 135px
    height: 135px
    border-radius: 110px
    user-select: none
    object-fit: cover
    border: 5px solid $avatarBorder
  &__name
    margin: .5em .8em .1em
    cursor: pointer
    user-select: none
    &:hover
      text-shadow: 3px 3px 5px rgba(86, 101, 115 ,.8)
  &__job-title
    margin: 0
    user-select: none
    font-weight: 300
    padding: 0 2em
    .link
      text-decoration: none
      &:focus
        outline: none
      &:hover
        font-weight: 700
      #vuejs-logo
        height: 15px
        object-fit: cover
        vertical-align: middle
    #vue-word
      color: $vueColor_2
    #lahzino
      color: $lahzino
  &__description
    width: 500px
    margin: 0
    user-select: none
    color: $description
    word-spacing: 3px
    letter-spacing: .8px
    #pwa-address
      color: transparent
      text-decoration: none
      &:focus
        outline: none
      &__logo
        height: 10px
        object-fit: cover
        &:hover
          filter: drop-shadow(3px 3px 2px #694BA6)
    #username
      cursor: pointer
      color: $vueColor_2
  .products-list-title
    margin-block-end: 0
  #socials-comp
    width: 50%
    margin-top: 8px
  #product-comp
    width: 50%
    margin-top: .1em
  @media screen and (max-width: 500px)
    #product-comp
      width: 80%
  @media screen and (min-width: 1000px)
    #product-comp
      width: 40%
</style>
