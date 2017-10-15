<template>
  <v-app>
    <!-- Toolbar -->
    <v-toolbar app>
      <v-toolbar-items xs12>
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

    <!-- Main Snakcbar -->
    <v-snackbar
      :color="snackbar.color"
      :multi-line=true
      v-model="snackbar.visible"
    >
      {{ snackbar.text }}
      <v-btn
        flat
        dark
        @click.native="snackbar.visible = false"
      >Close</v-btn>
    </v-snackbar>
  </v-app>
</template>

<script>
  import coffee from 'coffeescript'

  export default {
    methods: {
      eval () {
        try {
          eval(coffee.compile(this.console))
        } catch (err) {
          this.snackbar = {
            color: 'info',
            text: 'ERROR: ' + err.toString(),
            visible: true
          }
        }
        this.console = ''
      }
    },

    data () {
      return {
        console: '',
        snackbar: {
          color: 'info',
          text: 'Test',
          visible: false
        },
        title: 'Hijondo'
      }
    }
  }
</script>
