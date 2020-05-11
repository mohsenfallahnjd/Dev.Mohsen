<template>
    <div class="socials">
        <a
            v-for="(social, i) in socials"
            :key="i"
            :href="social.link"
            target="_blank"
            rel="noopener"
        >
            <img :src="social.img" :alt="`${social.name}-logo`" />
        </a>
    </div>
</template>

<script>
export default {
    name: 'Socials',
    data: () => ({
        socials: [
            {
                name: 'codepen',
                img: require('../assets/images/codepen.svg'),
                link: 'https://codepen.io/mohsenfallahnjd',
            },
            {
                name: 'dev.to',
                img: require('../assets/images/dev.svg'),
                link: 'https://dev.to/mohsenfallahnjd',
            },

            {
                name: 'github',
                img: require('../assets/images/github.svg'),
                link: 'https://github.com/mohsenfallahnjd',
            },
            {
                name: 'linkedin',
                img: require('../assets/images/linkedin.svg'),
                link: 'https://linkedin.com/in/mohsenfallahnjd',
            },
            {
                name: 'medium',
                img: require('../assets/images/medium.svg'),
                link: 'https://medium.com/@mohsenfallahnjd',
            },
            {
                name: 'spotify',
                img: require('../assets/images/spotify.svg'),
                link:
                    'https://open.spotify.com/user/72viqlcr5pqgmnmjtqh8w5980?si=n_n--xPIQv2Ga8epY9Wjfw',
            },
            {
                name: 'instagram',
                img: require('../assets/images/instagram.svg'),
                link: 'https://instagram.com/mohsenfallahnjd',
            },
            {
                name: 'telegram',
                img: require('../assets/images/telegram-app.svg'),
                link: 'https://telegram.me/mohsenfallahnjd',
            },
            {
                name: 'whatsapp',
                img: require('../assets/images/whatsapp.svg'),
                link: 'https://wa.me/00989197582087',
            },
            {
                name: 'twitter',
                img: require('../assets/images/twitter.svg'),
                link: 'https://twitter.com/mohsenfallahnjd',
            },
            {
                name: 'facebook',
                img: require('../assets/images/facebook.svg'),
                link: 'https://www.facebook.com/mohsenfallahnjd',
            },
            {
                name: 'email',
                img: require('../assets/images/email.png'),
                link: 'mailto:mohsenfallahnjd@gmail.com',
            },
        ],
    }),
}
</script>

<style lang="sass" scoped>
.socials
    width: 100%
    display: flex
    flex-direction: row
    justify-content: space-evenly
    flex-wrap: wrap
    align-items: center
    padding: .3em
    > a
        text-decoration: none
        padding: 0 .1em
        &:focus
            outline: none
        > img
            width: 30px
            object-fit: cover
        &:hover
            filter: drop-shadow(3px 3px 2px #694BA6)
</style>
