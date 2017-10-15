<template>
  <v-container grid-list-md>
    <v-layout row wrap>
      <!-- About -->
      <v-flex xs12 md6 offset-md3 lg4 offset-lg4 class="mb-5">
        <div class="text-xs-center">
          <img src="/hijondo.png" alt="Hijondo" width=100 class="mb-5">
        </div>

        <blockquote>
          &#8220;It sorta sounds like 'Hi, John Doe.'&#8221;
          <footer>
            <small>
              <em>&mdash;Hijondo</em>
            </small>
          </footer>
        </blockquote>
      </v-flex>

      <v-flex xs12 md6>
        <v-card>
          <v-card-title primary-title>
            <div>
              <h3 class="headline">Current Epic</h3>
              <p>The goal of this epic is to become completely self sufficient, entirely through online work. The following goals must be met:</p>
              <ul class="mb-4">
                <li>Food</li>
                <li>Shelter</li>
                <li>Utilities</li>
                <li>Phone</li>
                <li>Internet</li>
              </ul>
              <p>A stretch goal is to get free:</p>
              <ul class="mb-4">
                <li>Healthcare</li>
                <li>Clothing</li>
                <li>Computer</li>
                <li>Transportation</li>
              </ul>
              <p>Additionally, it would be great to have:</p>
              <ul>
                <li>6 months savings to cover the above</li>
                <li>1lb weed on standby</li>
              </ul>
            </div>
          </v-card-title>
        </v-card>
      </v-flex>

      <v-flex xs12 md6>
        <v-card>
          <v-card-title primary-title>
            <div>
              <h3 class="headline">Epic Logs</h3>
              <p>The following are measures I've taken towards the current Epic:</p>
              <ul></ul>
            </div>
          </v-card-title>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>
