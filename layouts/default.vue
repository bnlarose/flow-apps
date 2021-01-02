<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      color="primary"
      dark
      temporary
      absolute
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in sideNavItems"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      color="primary"
      dense
      dark
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title class="hidden-xs-only">
        <nuxt-link
          to="/"
          tag="span"
          style="cursor: pointer"
        >
          Flow Apps
        </nuxt-link>
      </v-toolbar-title>

      <v-spacer />
      <v-toolbar-items class="hidden-xs-only">
        <v-btn
          v-for="item in topNavItems"
          :key="item.title"
          :to="item.link"
          depressed
          color="primary"
        >
          <v-icon
            class="hidden-sm-only"
            left
          >
            {{ item.icon }}
          </v-icon>
          {{ item.title }}
        </v-btn>
      </v-toolbar-items>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer
      absolute
      dark
      color="primary"
      text-center
      app
    >
      <v-col cols="12" class="text-center">
        <v-dialog
          v-model="dialog"
          width="500"
        >
          <template v-slot:activator="{ on, attrs }">
            <v-btn
              color="primary"
              dark
              depressed
              small
              v-bind="attrs"
              v-on="on"
            >
              <strong>Flow Apps</strong>
            </v-btn>
          </template>

          <v-card>
            <v-card-title class="headline secondary lighten-2 text-center">
              Flow Apps
            </v-card-title>

            <v-card-text>
              Built for CWC by Elucidation Data Solutions
            </v-card-text>

            <v-divider />

            <v-card-actions>
              <v-spacer />
              <v-btn
                color="primary"
                text
                @click="dialog = false"
              >
                OK
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
        - <span>&copy; {{ new Date().getFullYear() }}</span>
      </v-col>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      drawer: false,
      dialog: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Home',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      title: 'Flow Apps'
    }
  },
  computed: {
    topNavItems () {
      const items = [
        { icon: 'mdi-lock-open', title: 'Sign In', link: '' }
      ]
      return items
    },
    sideNavItems () {
      const items = [
        { icon: 'mdi-apps', title: 'Home', to: '/' },
        { icon: 'mdi-lock-open', title: 'Sign In', link: '' }
      ]
      return items
    }
  }
}
</script>
