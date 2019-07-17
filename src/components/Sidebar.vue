<template>
  <v-navigation-drawer
    permanent
    fixed
    app
    width="250"
  >
        <v-text-field
        flat
        solo
        prepend-inner-icon="search"
        hide-details
        label="Search"
      ></v-text-field>
    <v-list dense subheader class="pt-0">
      <v-subheader>Tables</v-subheader>

      <v-list-group
        v-for="item in items"
        :key="item.name"
        v-model="item.active"
        no-action
      >
        <template v-slot:activator>
          <v-list-tile>
            <v-list-tile-content>
              <v-list-tile-title>{{ item.title }}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </template>

        <v-list-tile
          v-for="subItem in item.columns"
          :key="subItem.name"
          class="pl-2"
        >
          <v-list-tile-content>
            <v-list-tile-title>{{ subItem.name }} <span class="right">{{subItem.dataType}}</span></v-list-tile-title>
            <v-list-tile-sub-title>{{ subItem.datType }}</v-list-tile-sub-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list-group>

    </v-list>
  </v-navigation-drawer>

</template>

<script>

import _ from 'lodash'

export default {
  props: ['tables'],
  data() {
    return {
      right: null,
    }
  },

  computed: {
    items() {
      return _.map(this.tables, (table) => {
        return { name: table.name, title: _.startCase(table.name), icon: 'description', columns: table.columns}
      })
    }
  },
}

</script>


<style>

.v-list__group__items--no-action .v-list__tile {
  padding-left: 20px;
}

</style>
