<template>
  <div class="projects">
    <h1 class="subheading grey--text">Projects</h1>


      <v-container class="my-5">
        <v-expansion-panel>
          <v-expansion-panel-content v-for="project in myProjects" :key="project.title">
            <div slot="header">{{ project.title }}</div>
            <v-card>
              <v-card-text class="px-4 grey--text">
                <div class="font-weight-bold">due by {{ project.due }}</div>
                <div>{{ project.status }}</div>
              </v-card-text>
            </v-card>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-container>
  </div>
</template>

<script>


  export default {
    data() {
      return {
        projects: [
          { title: 'Design a new website', person: 'Paul', due: '1st June 2019', status: 'complete' },
          { title: 'Code up the homepage', person: 'Sam', due: '1st June 2019', status: 'ongoing' },
          { title: 'Design video thumbnails', person: 'Tom', due: '1st June 2019', status: 'overdue' },
          { title: 'Create a community forum', person: 'John', due: '20th Oct 2019', status: 'overdue' },
           { title: 'Design a new website', person: 'John', due: '1st June 2019', status: 'complete' },

      ]
      }
    },
    computed: {
      myProjects() {
        return this.projects.filter(project => {
          return project.person === 'John'
        })

      }
    }
  }
</script>