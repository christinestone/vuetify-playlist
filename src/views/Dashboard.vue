<template>
  <div class="dashboard">
    <h1 class="subheading grey--text">Dashboard</h1>
      <v-container class="my-5">

        <v-layout row class="mb-3">
          <v-btn small flat color="grey" @click="sortBy('title')">
            <v-icon left small>folder</v-icon>
            <span class="caption text-lowercase">By project name</span>
          </v-btn>
          <v-btn small flat color="grey" @click="sortBy('person')">
            <v-icon left small>person</v-icon>
            <span class="caption text-lowercase">By person</span>
          </v-btn>
          <v-btn small flat color="grey" @click="sortBy('due')">
            <v-icon left small>calendar_today</v-icon>
            <span class="caption text-lowercase">By due date</span>
          </v-btn>
          <v-btn small flat color="grey" @click="sortBy('status')">
            <v-icon left small>done</v-icon>
            <span class="caption text-lowercase">By status</span>
          </v-btn>
        </v-layout>

        <v-card flat v-for="project in projects" :key="project.title">
          <v-layout row wrap :class="`pa-3 project ${project.status}`">
            <v-flex xs12 md6>
              <div class="caption grey--text">Project Title</div>
              <div >{{ project.title }}</div>
            </v-flex>
            <v-flex xs6 sm4 md2>
              <div class="caption grey--text">Person</div>
              <div>{{ project.person }}</div>
            </v-flex>
            <v-flex xs6 sm4 md2>
              <div class="caption grey--text">Due by</div>
              <div>{{ project.due }}</div>
            </v-flex>
            <v-flex xs6 sm4 md2>
              <div class="right">
                <v-chip small :class="`${project.status} white--text caption my-2`">{{ project.status }}</v-chip>
              </div>
            </v-flex>
          </v-layout>
          <v-divider></v-divider>
        </v-card>

      </v-container>
  </div>
</template>

<script>


  export default {
    data() {
      return {
        projects: [
          { title: 'Design a new website', person: 'The Net Ninja', due: '1st June 2019', status: 'complete' },
          { title: 'Code up the homepage', person: 'Sam', due: '1st June 2019', status: 'ongoing' },
          { title: 'Design video thumbnails', person: 'Tom', due: '1st June 2019', status: 'overdue' },
          { title: 'Create a community forum', person: 'John', due: '20th Oct 2019', status: 'overdue' },

      ]
      }
    },
    methods: {
      sortBy(itemType) {
        // sort fn is normal js fn which sorts items in an array
        this.projects.sort((a,b) => a[itemType] < b[itemType] ? -1 : 1)
      }
    }
  }
</script>
<style>
  .project.complete {
    border-left: 4px solid #3cd1c2;
  }
  .project.ongoing {
    border-left: 4px solid orange;
  }
  .project.overdue {
    border-left: 4px solid tomato;
  }
  .v-chip.complete {
    background: #3cd1c2;
  }
  .v-chip.ongoing {
    background: #ffaa2c;
  }
  .v-chip.overdue {
    background: #f83e70;
  }
</style>
