<template>
    <v-app>
        <v-navigation-drawer persistent
                             :mini-variant="miniVariant"
                             :clipped="clipped"
                             v-model="drawer"
                             enable-resize-watcher
                             fixed
                             app>
            <v-list>
                <v-list-tile value="true"
                             v-for="(item, i) in items"
                             :key="i"
                             v-bind:to="item.to">
                    <v-list-tile-action>
                        <v-icon v-html="item.icon"></v-icon>
                    </v-list-tile-action>
                    <v-list-tile-content>
                        <v-list-tile-title v-text="item.title"></v-list-tile-title>
                    </v-list-tile-content>
                </v-list-tile>
            </v-list>
        </v-navigation-drawer>
        <v-toolbar app :clipped-left="clipped">
            <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
            <v-toolbar-title v-text="title"></v-toolbar-title>
            <v-spacer></v-spacer>
        </v-toolbar>
        <v-content>
            <router-view/>
        </v-content>
        <!--<v-footer :fixed="fixed" app>-->
        <!--<span>&copy; 2018</span>-->
        <!--</v-footer>-->
    </v-app>
</template>

<script>
    export default {
        name: 'App',
        data() {
            return {
                clipped: false,
                drawer: true,
                fixed: false,
                items: [
                    {
                        icon: 'bubble_chart',
                        title: 'Hello!',
                        to: "/"
                    },
                    // {
                    //     icon: 'devices',
                    //     title: 'Plataforma',
                    //     to: "/plataforma"
                    // },
                    {
                        icon: 'bubble_chart',
                        title: 'Sobre',
                        to: "/sobre"
                    }
                ],
                miniVariant: false,
                right: true,
                rightDrawer: false,
                title: 'Qual a Nota?'
            }
        }
    }
</script>
