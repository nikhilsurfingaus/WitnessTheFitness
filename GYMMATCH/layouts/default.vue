<template>
  <v-app dark>
    <!-- <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
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
      :clipped-left="clipped"
      fixed
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn
        icon
        @click.stop="miniVariant = !miniVariant"
      >
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-app-bar> -->
    <v-main>
      <Nuxt />
    </v-main>
    <v-bottom-navigation
      app
      fixed
      v-model="value"
      :input-value="active"
      color="#E94057"
      shift
      grow
      height="60px"
    >
      <v-btn to="/leaderboard" nuxt>
        <span>Leaderboard</span>

        <v-icon>mdi-chart-bar</v-icon>
      </v-btn>
      
      <v-btn to="/match">
        <span>Matching</span>
        
        <v-icon>mdi-human-greeting-proximity</v-icon>
      </v-btn>

      <v-btn to="/friends" nuxt>
        <span>Friends</span>
        
        <v-icon>mdi-account-group</v-icon>
      </v-btn>

      <v-btn to="/chat" nuxt>
        <span>Messages</span>
        
        <v-icon>mdi-message-processing</v-icon>
      </v-btn>

      <v-btn to="/profile" nuxt>
        <span>Profile</span>
        
        <v-icon>mdi-account</v-icon>
      </v-btn>
    </v-bottom-navigation>
    <v-footer
      padless
      absolute
      app
    >
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      value: 0,
      active: true,
      items: [
        {
          icon: 'mdi-apps',
          title: 'HOME',
          to: '/'
        },
        {
          icon: 'mdi-apps',
          title: 'Leaderboard',
          to: '/leaderboard'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'GYMATCH'
    }
  }
}
</script>
