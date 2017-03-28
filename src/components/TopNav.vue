<template>
    <div>
        <div class="topNav">
            <span v-on:click="toggleMenu" class="navLink clickable"><icon name="bars" scale="2" ></icon></span>

        </div>
        <div v-if="showName">
            <sideNav></sideNav>
        </div>
    </div>
</template>

<script>
    import sideNav from './SideNav'
    export default {
        name: 'nav',
        components: {
            sideNav
        },
        data () {
            return {
                showName: false
            }
        },
        methods: {
            toggleMenu: function() {
                this.showName = !this.showName;
            }
        }

    }
</script>

<style lang="sass">

</style>