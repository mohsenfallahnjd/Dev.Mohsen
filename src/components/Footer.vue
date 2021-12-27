<template>
    <div class="footer">
        <div class="copy-right">
            © {{ yearCopyRight }} by #MohsenFallahnejad
        </div>
    </div>
</template>

<script>
export default {
    name: 'Footer',
    computed: {
        yearCopyRight() {
            return new Date().getFullYear()
        },
    },
}
</script>

<style lang="sass" scoped>
$bgColor: #fafafa
$description: #566573
.footer
    width: 100%
    height: 100%
    display: flex
    flex-direction: column
    align-items: center
    justify-content: space-between
    background-color: $bgColor
    .copy-right
        font-size: 13px
        color: lighten($description,10% )
        margin: auto
</style>
