<template>
  <v-card
    class="mx-auto"
    max-width="300"
    tile
  >
    <v-list dense>
      <v-subheader>Locations</v-subheader>
      <v-list-item-group
        v-model="selectedItem"
        color="primary"
      >
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-icon>
            <v-icon v-text="item.icon"></v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title v-text="item.text"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-card>
</template>

<script>
  export default {
    data: () => ({
      selectedItem: 5,
      items: [
        { text: 'Choose', icon: 'mdi-crosshairs-gps' },
        { text: 'Kuala Lumpur', icon: '', to: '/' },
        { text: 'George Town', icon: '', to: '/' },
        { text: 'Johor Bahru', icon: '', to: '/' },
        { text: 'Ipoh', icon: '', to: '/' },
        { text: 'Load more', icon: 'mdi-refresh', to: '/' },
      ],
    }),
  }
</script>
