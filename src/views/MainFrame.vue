<template>
 <v-app id="inspire">
    <v-app-bar
      class="px-3"
      color="black"
      flat
      density="prominent"
    >
        <v-img
          class="mt-lg-7"
          height="50%"
          src="https://status.webex.com/img/webexbycisco-3d_wh.ad601405.png"
          to="/test"
        ></v-img>
      <v-tabs
        align-tabs="center"
        color="blue-darken-2"
      >
        <v-tab
          v-for="link in links"
          :key="link"
          class="ciscofont text-h5"
          :ripple="false"
        >
          {{ link }}
        </v-tab>
      </v-tabs>
      <v-spacer></v-spacer>

      <v-tab>
      </v-tab>
    </v-app-bar>
    <v-main class="bg-grey-lighten-3 mainframe">
      <v-container>
        <v-row>
          <!-- Used for Framing   -->
          <v-col
            cols="3"
            sm="2"
          >
            <v-sheet
              rounded="lg"
              min-height="268"
              color="transparent"
            >
              <!--  -->
            </v-sheet>
          </v-col>
          <!-- Used for Framing - Center  -->
          <v-col
            cols="12"
            sm="8"
          >
          <ServiceStatus></ServiceStatus>
          </v-col>
          <!-- Used for Framing   -->
          <v-col
            cols="12"
            sm="2"
          >
            <v-sheet
              rounded="lg"
              min-height="268"
              color="transparent"
            >

            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>

import ServiceStatus from "@/components/ServiceStatus.vue";

export default {
  name: "MainFrame",
  components: {
    ServiceStatus
  },
  data: () => ({
      links: [
        'Service Status',
        'Incident History',
        'Maintenance',
        'Calendar',
        'Help',
      ],
      status_card:{
        wx_number: '005'
      },


    }),
}
</script>

<style scoped>

.mainframe {
  background: url('../assets/background.png');
}
.ciscofont{
  font-family: "CiscoSansTT Regular";
}
.v-tab {
text-transform: none !important;
}
</style>
