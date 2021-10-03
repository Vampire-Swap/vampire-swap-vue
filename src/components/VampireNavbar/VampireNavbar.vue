<template>
    <div>
        <v-app-bar class="elevation-6 rounded-lg ma-2" absolute color="blue-grey darken-4">
            <v-app-bar-nav-icon @click.stop="drawer = !drawer" class="d-md-none" />
            <v-toolbar-title class="font-weight-bold">Vampire Swap</v-toolbar-title>
            <v-list nav color="blue-grey darken-4" class="d-none d-md-flex" height="inherit">
                <v-list-item v-for="(link, i) in links" :key="'navbar-link-' + i" :to="link.url">
                    <v-list-item-title class="font-weight-bold">{{ link.name }}</v-list-item-title>
                </v-list-item>
            </v-list>
        </v-app-bar>

        <v-navigation-drawer class="rounded-lg ma-2" v-model="drawer" absolute temporary color="blue-grey darken-4">
            <v-list nav dense>
                <v-list-item v-for="(link, i) in links" :key="'navbar-link-' + i" :to="link.url">
                    <v-list-item-title class="font-weight-bold">{{ link.name }}</v-list-item-title>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { Link } from './Link';

export default Vue.extend({
    name: 'VampireNavbar',

    data: () => {
        return {
            selectedLink: 0,
            drawer: false,
            group: null,
            links: [
                new Link('Home', '/'),
                new Link('Blood Pools', '/pools'),
                new Link('Pumpkin Patches', '/patches'),
                new Link('Roadmap', '/roadmap')
            ]
        }
    },

    watch: {
        group() {
            this.drawer = false;
        }
    }
})
</script>


<style lang="scss" scoped>
    .links-holder {
        margin-left: 2rem;
        align-content: space-around;
        justify-content: space-around;
    }

    .links-holder a {
        margin-right: 0.7rem;
        text-decoration: none;
    }

    .links-holder a:hover {
        color: #E57373 !important;
    }
</style>