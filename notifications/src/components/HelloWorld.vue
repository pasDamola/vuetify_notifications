<template>
<v-container>
  <v-layout row>
    <v-flex xs12 sm6 offset-sm3>
      <!-- <v-card> -->
        <v-toolbar color="cyan" dark>
          <!-- <v-toolbar-side-icon></v-toolbar-side-icon> -->

          <v-toolbar-title>Notifications</v-toolbar-title>

          <v-spacer></v-spacer>

          <v-btn icon>
            <v-icon>search</v-icon>
          </v-btn>
        </v-toolbar>

        <v-list three-line>
          <template v-for="(item, index) in items">
            <v-subheader
              v-if="item.header"
              :key="item.header"
            >
              {{ item.header }}
            </v-subheader>

            <v-divider
              v-else-if="item.divider"
              :key="index"
              :inset="item.inset"
            ></v-divider>

            <v-list-tile
              v-else
              :key="item.title"
             avatar
            >
            <i class="material-icons">notifications</i>
              <v-list-tile-avatar>
                <!-- <img :src="item.avatar"> -->
              </v-list-tile-avatar>

              <v-list-tile-content>
                <v-list-tile-title v-html="item.title"></v-list-tile-title>
                <v-list-tile-sub-title v-html="item.subtitle"></v-list-tile-sub-title>
              </v-list-tile-content>
              
            </v-list-tile>
          </template>
        </v-list>
        <v-list three-line>
          <template v-for="(item, index) in items">
            <v-subheader
              v-if="item.header"
              :key="item.header"
            >
              <!-- {{ item.header }} -->
              This week
            </v-subheader>

            <v-divider
              v-else-if="item.divider"
              :key="index"
              :inset="item.inset"
            ></v-divider>

            <v-list-tile
              v-else
              :key="item.title"
              avatar
            >

            <i class="material-icons">notifications</i>
              <v-list-tile-avatar>
                <!-- <img :src="item.avatar"> -->
              </v-list-tile-avatar>

              <v-list-tile-content>
                <v-list-tile-title v-html="item.title"></v-list-tile-title>
                <v-list-tile-sub-title v-html="item.subtitle"></v-list-tile-sub-title>
              </v-list-tile-content>
            </v-list-tile>
            
          </template>
          <p></p>
         <a href="#"> <i class="material-icons" id="navigate" title="see older notifications">arrow_forward</i></a>
          <!-- <i class="fas fa-chevron-circle-right"></i> -->
        </v-list>
      <!-- </v-card> -->
    </v-flex>
  </v-layout>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {
        items: [
          { header: 'Today' },
          {
            avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
            title: 'Approved Vendor Recommendation',
            subtitle: "<span class='text--primary'>CEO</span> &mdash; Your vendor recommendation has been approved",
          },
          { divider: true, inset: true },
          {
            avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
            title: 'Approved Procurement plan',
            subtitle: "<span class='text--primary'>HOP</span> &mdash; Procurement plan for the department has been approved."
          },
          { divider: true, inset: true },
          {
            avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
            title: 'Rejected Extra Budgetary',
            subtitle: "<span class='text--primary'>CEO</span> &mdash; Provide valid justification for your extra budgetary plan"
          }
        ]
      }
    }
  }
</script>

<style>
#navigate{
 margin-left : 50%;
}
</style>
