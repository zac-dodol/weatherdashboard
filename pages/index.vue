<template>
  <v-row>
    <v-col cols="12">
      <v-banner single-line>
        <v-icon slot="icon" color="info" size="36"> mdi-crosshairs-gps </v-icon>
        Kuala Lumpur

        <template v-slot:actions>
          <v-col cols="4">
            <v-text-field label="Search" clearable></v-text-field>
          </v-col>
          <v-btn icon to="/search">
            <v-icon>mdi-magnify</v-icon>
          </v-btn>
        </template>
      </v-banner>
    </v-col>

    <v-col v-for="n in 1" :key="n" cols="4" style="margin: auto">
      <v-card class="mx-auto" max-width="400" outlined tile>
        <v-list-item two-line>
          <v-list-item-content>
            <v-list-item-title class="text-h5">
              Kuala Lumpur
            </v-list-item-title>
            <v-list-item-subtitle
              >Mon, 12:30 PM, Mostly sunny</v-list-item-subtitle
            >
          </v-list-item-content>
        </v-list-item>

        <v-card-text>
          <v-row align="center">
            <v-col cols="6">
              <v-img
                src="https://cdn.vuetifyjs.com/images/cards/sun.png"
                alt="Sunny image"
                width="92"
              ></v-img>
            </v-col>
            <v-col class="text-h2" cols="6"> 23&deg;C </v-col>
          </v-row>
        </v-card-text>

        <v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-send</v-icon>
            </v-list-item-icon>
            <v-list-item-subtitle>23 km/h</v-list-item-subtitle>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-cloud-download</v-icon>
            </v-list-item-icon>
            <v-list-item-subtitle>48%</v-list-item-subtitle>
          </v-list-item>
        </v-list-item>

        <v-divider></v-divider>

        <v-list class="transparent">
          <v-list-item v-for="item in forecast" :key="item.day">
            <v-list-item-title>{{ item.day }}</v-list-item-title>

            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-subtitle class="text-right">
              {{ item.temp }}
            </v-list-item-subtitle>
          </v-list-item>
        </v-list>

        <!-- <v-slider
          v-model="time"
          :max="6"
          :tick-labels="labels"
          class="mx-4"
          ticks
          track-fill-color="#ffffff33"
        ></v-slider> -->

        <v-divider></v-divider>

        <v-card-actions>
          <v-btn text color="primary" to="/about"> SEE MORE... </v-btn>
          <v-spacer />
        </v-card-actions>
      </v-card>
    </v-col>

    <v-col cols="12">
      <!-- <v-card-actions>
      <v-spacer />
      <v-btn color="amber" nuxt to="/about"> About </v-btn>
      <v-btn color="primary" nuxt to="/inspire"> Inspire </v-btn>
      <v-btn color="success" nuxt to="/weather"> Home </v-btn>
      <v-btn color="info" nuxt to="/time"> Time </v-btn>
    </v-card-actions> -->
    </v-col>
  </v-row>
</template>


<script>
export default {
  data() {
    return {
      labels: ["SU", "MO", "TU", "WED", "TH", "FR", "SA"],
      time: 0,
      forecast: [
        {
          day: "Tuesday",
          icon: "mdi-white-balance-sunny",
          temp: "24\xB0/30%",
        },
        {
          day: "Wednesday",
          icon: "mdi-weather-rainy",
          temp: "22\xB0/62%",
        },
        { day: "Thursday",
          icon: "mdi-cloud",
          temp: "25\xB0/36%"
        },
        { day: "Friday",
          icon: "mdi-weather-lightning",
          temp: "25\xB0/75%"
        },
      ],
    };
  },
};
</script>
