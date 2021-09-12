<template>
  <v-row justify="center" align="center">
    <div>
      <v-app-bar color="deep-purple accent-4" dense dark>
        <v-app-bar-nav-icon></v-app-bar-nav-icon>

        <v-toolbar-title>Page title</v-toolbar-title>

        <v-spacer></v-spacer>

        <v-btn icon>
          <v-icon>mdi-heart</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>

        <v-menu left bottom>
          <template v-slot:activator="{ on, attrs }">
            <v-btn icon v-bind="attrs" v-on="on">
              <v-icon>mdi-dots-vertical</v-icon>
            </v-btn>
          </template>

          <v-list>
            <v-list-item v-for="n in 5" :key="n" @click="() => {}">
              <v-list-item-title>Option {{ n }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-app-bar>
    </div>
    <v-col>
      <v-card class="logo py-4 d-flex justify-center">
        <img src="/v.png" alt="Vuetify.js" class="mb-5" />
        <blockquote class="blockquote">
          &#8220;First, solve the problem. Then, write the code.&#8221;
          <footer>
            <small>
              <em>&mdash;John Johnson</em>
            </small>
          </footer>
        </blockquote>
        <v-card-actions>
          <v-spacer />
          <v-btn color="amber" nuxt to="/about"> About </v-btn>
          <v-btn color="primary" nuxt to="/inspire"> Inspire </v-btn>
          <v-btn color="success" nuxt to="/weather"> Weather </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>

    <div class="secondCard">
      <v-col>
        <v-card class="logo py-4 d-flex justify-center">
          <p>date</p>
        </v-card>
      </v-col>
      <v-col>
        <v-card class="logo py-4 d-flex justify-center">
          <p>date</p>
        </v-card>
      </v-col>
      <v-col>
        <v-card class="logo py-4 d-flex justify-center">
          <p>date</p>
        </v-card>
      </v-col>
      <v-col>
        <v-card class="logo py-4 d-flex justify-center">
          <p>date</p>
        </v-card>
      </v-col>
    </div>
  </v-row>
</template>
