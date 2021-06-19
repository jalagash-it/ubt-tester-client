<template>
  <v-container>
    <!-- <v-navigation-drawer>
            <v-divider></v-divider>
            <v-list nav dense>
                <v-list-item @click="changeCurrentComponent('userProfiles')">
                    <v-list-item-icon>
                        <v-icon color="white" small>mdi-lightbulb</v-icon>
                    </v-list-item-icon>
                    <v-list-item-title class="title">Profile</v-list-item-title>
                </v-list-item>
                <v-list-item @click="changeCurrentComponent('adminLessons')">
                    <v-list-item-icon>
                        <v-icon color="white" small>mdi-lightbulb</v-icon>
                    </v-list-item-icon>
                    <v-list-item-title class="title">Lessons</v-list-item-title>
                </v-list-item>
                <v-list-item @click="changeCurrentComponent('adminUsers')">
                    <v-list-item-icon>
                        <v-icon color="white" small>mdi-lightbulb</v-icon>
                    </v-list-item-icon>
                    <v-list-item-title class="title">Users</v-list-item-title>
                </v-list-item>
            </v-list>
        </v-navigation-drawer> -->
        <!-- <v-main>
            <component :is="child"/>
        </v-main> -->
    <v-card>
      <v-toolbar>
        <v-toolbar-title>Dashboard</v-toolbar-title>
      </v-toolbar>
      <v-tabs vertical >
        <v-tab>
          <v-icon left> mdi-account </v-icon>
          Profile
        </v-tab>
        <v-tab>
          <v-icon left> mdi-book-open-outline </v-icon>
          Lessons
        </v-tab>
        <v-tab>
          <v-icon left> mdi-account-group </v-icon>
          Users
        </v-tab>
        <v-tab-item class="pl-16">
          <userProfiles></userProfiles>
        </v-tab-item>
        <v-tab-item class="pl-16">
         <adminLessons></adminLessons>
        </v-tab-item>
        <v-tab-item class="pl-16">
          <adminUsers></adminUsers>
        </v-tab-item>
      </v-tabs>
    </v-card>
  </v-container>
</template>
<script>
import userProfiles from '~/pages/user/profile/index.vue'
import adminLessons from '~/pages/user/admin/lessons/index.vue'
import adminUsers from '~/pages/user/admin/users/index.vue'
export default {
    data(){
        return{
            child:'userProfiles'
        }
    },
    methods:{
        changeCurrentComponent(key_){
            this.child = key_;
        }
    },
    components: {
        userProfiles,
        adminLessons,
        adminUsers
    }
}
</script>