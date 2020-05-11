<template>
    <div class="home">
        <div id="copy-notif">username copy to your clipboard!</div>
        <img
            id="avatar"
            src="../assets/images/mohsen.jpg"
            alt="mohsen-avatar"
        />

        <h1 id="name">Mohsen Fallahnejad</h1>

        <h3 id="job-title">
            Front-end,
            <a
                id="vue-word"
                href="https://vuejs.org/"
                target="_blank"
                rel="noopener"
            >
                Vue.js
                <img src="../assets/images/vue-js.svg" alt="vuejs-logo" />
            </a>
            | Public Relations Manager at
            <a
                id="lahzino"
                href="https://lahzino.ir/"
                target="_blank"
                rel="noopener"
            >
                Lahzino.ir
            </a>
        </h3>

        <p class="description">
            <!-- I try to gain experience and learn different skills in different
            fields related to the field I work in. That way, both my mind goes
            out of one-dimensionality and it makes me more creative in my work.
            Everything in the tech world attracts me and my laptop is my best
            friend. -->
            in rel with
            <a
                href="https://web.dev/progressive-web-apps/"
                target="_blank"
                rel="noopener"
            >
                <img
                    id="pwa-logo"
                    src="../assets/images/PWA.png"
                    alt="pwa-logo"
                />
            </a>
        </p>
        <p id="id-text" class="description">
            I'm on all Social Medias<br />with:
            <span id="username" @click="copyUsername">@mohsenfallahnjd</span>
        </p>
        <div id="socials-comp"><Socials /></div>
        <h3 class="products-list-title">--- Products List ---</h3>
        <div id="link-comp"><Link /></div>
    </div>
</template>

<script>
import Socials from '@/components/Socials.vue'
import Link from '@/components/Link.vue'
export default {
    name: 'Home',
    components: {
        Socials,
        Link,
    },
    methods: {
        copyUsername() {
            navigator.clipboard.writeText('@mohsenfallahnjd')
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
  text-align: center
  padding: 3em 0
  #avatar
    width: 135px
    height: 135px
    border-radius: 110px
    user-select: none
    object-fit: cover
    border: 5px solid $avatarBorder
  #name
    margin-block-start: .5em
    margin-block-end: .1em
    cursor: pointer
    user-select: none
    &:hover
      text-shadow: 3px 3px 5px rgba(86, 101, 115 ,.8)
  #job-title
    margin-block-start: 0
    user-select: none
    margin-block-end: 0
    font-weight: 300
    #vue-word
      color: $vueColor_2
    #lahzino
      color: $lahzino
    > a
      text-decoration: none
      &:focus
        outline: none
      &:hover
        font-weight: 700
      > img
        height: 15px
        object-fit: cover
        vertical-align: middle
  .description
    margin: 0
    user-select: none
    color: $description
    text-rendering: optimizeLegibility
    width: 500px
    text-align: center
    word-spacing: 3px
    letter-spacing: .8px
    > a
      color: transparent
      text-decoration: none
      &:focus
        outline: none
      #pwa-logo
        height: 10px
        object-fit: cover
        &:hover
          filter: drop-shadow(3px 3px 2px #694BA6)
    #username
      cursor: pointer
      color: $vueColor_2
  #copy-notif
    width: 69%
    height: 50px
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
  .products-list-title
    margin-block-end: 0
  #socials-comp
    width: 50%
    margin-top: 8px
  #link-comp
    width: 50%
    margin-top: .1em
  @media screen and (max-width: 500px)
    #job-title ,#id-text
      padding: 0px 3em
    #link-comp
      width: 80%
  @media screen and (min-width: 1000px)
    #link-comp
      width: 40%
</style>
