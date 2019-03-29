<template>
  <div class="team">
    <h1 class="subheading grey--text">Team</h1>
      <v-container class="my-5">
          <v-layout row wrap>
              <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name">
                 <v-card flat class="text-xs-center ma-3">
                     <v-responsive class="pt4">
                         <v-avatar size="100" class="grey lighten-2 mt-4">
                             <img :src="person.avatar">
                         </v-avatar>
                     </v-responsive>
                     <v-card-text>
                      <div class="subheading">{{ person.name }}</div>
                      <div class="grey--text">{{ person.role }}</div>
                     </v-card-text>
                     <v-card-actions>
                         <v-btn flat color="grey">
                             <v-icon small left>message</v-icon>
                             <span>Message</span>
                         </v-btn>
                     </v-card-actions>
                 </v-card>

              </v-flex>
            </v-layout>
      </v-container>
  </div>
</template>

<script>


  export default {
    data() {
        return {
            team: [
                { name: 'John', role: 'web dev' , avatar: '/avatar-1.png'},
                { name: 'Paul', role: 'graphic designer' , avatar: '/avatar-2.png'},
                { name: 'George', role: 'web dev' , avatar: '/avatar-3.png'},
                { name: 'Ringo', role: 'sales' , avatar: '/avatar-4.png'}
            ]
        }
    }
  }
</script>