<template>
  <div class="projects">
    <h1 class="subheading grey--text">Projects</h1>

    <v-container class="my-5">

      <v-expansion-panel>
        <v-expansion-panel-content v-for="project in myProjects" :key="project.title">
          <div slot="header">{{project.title}}</div>
          <v-card>
            <v-card-text class="px-4 grey--text">
              <div class="font-weight-bold">due by {{ project.due }}</div>
              <div>{{ project.content }}</div>
            </v-card-text>
          </v-card>
        </v-expansion-panel-content>
      </v-expansion-panel>

    </v-container>

  </div>
</template>

<script>
export default{
  data(){
    return{
      projects: [
        { title: 'Design a new website', person: 'The Net Ninja', due: '1st Jan 2019', status: 'ongoing', content: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Asperiores neque blanditiis doloremque nisi tempora. Autem sapiente tempora facere veritatis. Sapiente ipsam deserunt eum corrupti, aliquam iure! Voluptate esse facere corrupti." },
        { title: 'Code up the homepage', person: 'Chun Li', due: '10th Dec 2018', status: 'complete', content: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Asperiores neque blanditiis doloremque nisi tempora. Autem sapiente tempora facere veritatis. Sapiente ipsam deserunt eum corrupti, aliquam iure! Voluptate esse facere corrupti." },
        { title: 'Zizo a new website', person: 'Anny Net Ninja', due: '1st Jan 2019', status: 'ongoing', content: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Asperiores neque blanditiis doloremque nisi tempora. Autem sapiente tempora facere veritatis. Sapiente ipsam deserunt eum corrupti, aliquam iure! Voluptate esse facere corrupti." },
        { title: 'Baby up the homepage', person: 'Mon Li', due: '10th Dec 2018', status: 'overdue', content: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Asperiores neque blanditiis doloremque nisi tempora. Autem sapiente tempora facere veritatis. Sapiente ipsam deserunt eum corrupti, aliquam iure! Voluptate esse facere corrupti." },
        { title: 'Baby up the homepage', person: 'The Net Ninja', due: '9th Dec 2020', status: 'overdue', content: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Asperiores neque blanditiis doloremque nisi tempora. Autem sapiente tempora facere veritatis. Sapiente ipsam deserunt eum corrupti, aliquam iure! Voluptate esse facere corrupti." },
      ]
    }
  },
  computed: {
    myProjects(){
      return this.projects.filter(project =>{
        return project.person === 'The Net Ninja'
      })
    }
  }
}
</script>
