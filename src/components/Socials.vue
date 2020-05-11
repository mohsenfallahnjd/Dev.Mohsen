<template>
    <div class="socials">
        <a
            v-for="(social, i) in socialsData"
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
    props: {
        socialsData: {
            type: Array,
        },
    },
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
