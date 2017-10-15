<template>
  <v-app>
    <!-- Left Drawer -->
    <v-navigation-drawer
      persistent
      :mini-variant="true"
      v-model="drawer"
      app
    >
      <v-list>
        <v-list-tile
          router
          :to="item.to"
          :key="i"
          v-for="(item, i) in items"
          exact
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>

    <!-- Toolbar -->
    <v-toolbar app>
      <v-toolbar-items>
        <v-text-field
          v-model="console"
          @keyup.enter="eval"
          name="field-command"
          prepend-icon="code"
          autofocus
          clearable
        ></v-text-field>
      </v-toolbar-items>
      <v-spacer></v-spacer>
    </v-toolbar>

    <!-- Main container -->
    <main>
      <v-content>
        <v-container>
          <nuxt />
        </v-container>
      </v-content>
    </main>

    <!-- Footer -->
    <v-footer app>
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
  import coffee from 'coffeescript'

  export default {
    methods: {
      eval () {
        eval(coffee.compile(this.console))
        this.console = ''
      }
    },

    data () {
      return {
        console: '',
        drawer: true,
        items: [
          { icon: 'code', title: 'Dashboard', to: '/' },
          { icon: 'info', title: 'About', to: '/about' }
        ],
        title: 'Hijondo'
      }
    }
  }
</script>
