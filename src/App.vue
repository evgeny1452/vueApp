<template>
  <v-app>
    <v-navigation-drawer
            app
            v-model="drawer"
    >

      <v-list>
        <v-list-item
                v-for="link in links"
                :key="link.title"
                :to="link.url"

        >
          <v-list-item-icon>
            <v-icon left >mdi-{{link.icon}}</v-icon>
<!--            <v-icon>mdi-lock</v-icon>-->
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title v-text="link.title"></v-list-item-title>
          </v-list-item-content>

        </v-list-item>
      </v-list>


<!--      &#45;&#45;&#45;&#45;&#45;&#45;&#45;&#45;-->
<!--      <v-list>-->
<!--        <v-list-item-->
<!--                v-for="item in items"-->
<!--                :key="item.title"-->
<!--                @click="item.icon = !item.icon"-->
<!--        >-->
<!--          <v-list-item-icon>-->
<!--            <v-icon v-if="item.icon" color="pink">mdi-star</v-icon>-->
<!--          </v-list-item-icon>-->

<!--          <v-list-item-content>-->
<!--            <v-list-item-title v-text="item.title"></v-list-item-title>-->
<!--          </v-list-item-content>-->

<!--          <v-list-item-avatar>-->
<!--            <v-img :src="item.avatar"></v-img>-->
<!--          </v-list-item-avatar>-->
<!--        </v-list-item>-->
<!--      </v-list>-->

    </v-navigation-drawer>

    <v-app-bar
            color="primary"
            dense
            dark
            app
    >
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Page title</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-menu left bottom>
        <template v-slot:activator="{ on }">
          <v-btn icon v-on="on">
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item
                  v-for="n in 2"
                  :key="n"
                  @click="() => {}"
          >
            <v-list-item-title>Option {{ n }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>


    <v-content>
      <v-container fluid>
        <router-view></router-view>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        drawer: false,
        items: [
          { icon: true, title: 'Jason Oner', avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg' },
          { icon: false, title: 'Travis Howard', avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg' },
          { icon: false, title: 'Ali Connors', avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg' },
          { icon: false, title: 'Cindy Baker', avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg' },
        ],
        links: [
          {title: 'Login', icon: 'lock', url: '/login'},
          {title: 'Registration', icon: 'face', url: '/registration'},
          {title: 'Orders', icon: 'bookmark-border', url: '/orders'},
          {title: 'New ad', icon: 'note-add', url: '/new'},
          {title: 'My ads', icon: 'list', url: '/list'},
        ]
      }
    },
    methods: {
    }
  }
</script>

<style lang="scss">
</style>
