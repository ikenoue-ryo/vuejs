<template>
  <div class="home">
    <h1 class="subheading grey--text">Dashboard</h1>

    <v-container class="my-5">

      <v-layout row class="mb-3">

        <v-tooltip top>
          <v-btn small flat color="grey" @click="sortBy('title')" slot="activator">
            <v-icon left small>folder</v-icon>
            <span class="caption text-lowercase">By project name</span>
          </v-btn>
          <span>Sort projects by project name</span>
        </v-tooltip>

        <v-tooltip top>
          <v-btn small flat color="grey" @click="sortBy('person')" slot="activator">
            <v-icon left small>person</v-icon>
            <span class="caption text-lowercase">By person</span>
          </v-btn>
          <span>Sort projects by person</span>
        </v-tooltip>

      </v-layout>

      <v-card flat v-for="project in projects" :key="project.title">
        <v-layout row wrap :class="`pa-3 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text">Project title</div>
            <div>{{ project.title }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Person</div>
            <div>{{ project.person }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Due by</div>
            <div>{{ project.due }}</div>
          </v-flex>
          <v-flex xs2 sm4 md2>
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
export default{
  data(){
    return {
      projects: [
        { title: 'Design a new website', person: 'The Net Ninja', due: '1st Jan 2019', status: 'ongoing', content: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Asperiores neque blanditiis doloremque nisi tempora. Autem sapiente tempora facere veritatis. Sapiente ipsam deserunt eum corrupti, aliquam iure! Voluptate esse facere corrupti." },
        { title: 'Code up the homepage', person: 'Chun Li', due: '10th Dec 2018', status: 'complete', content: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Asperiores neque blanditiis doloremque nisi tempora. Autem sapiente tempora facere veritatis. Sapiente ipsam deserunt eum corrupti, aliquam iure! Voluptate esse facere corrupti." },
        { title: 'Zizo a new website', person: 'Anny Net Ninja', due: '1st Jan 2019', status: 'ongoing', content: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Asperiores neque blanditiis doloremque nisi tempora. Autem sapiente tempora facere veritatis. Sapiente ipsam deserunt eum corrupti, aliquam iure! Voluptate esse facere corrupti." },
        { title: 'Baby up the homepage', person: 'Mon Li', due: '10th Dec 2018', status: 'overdue', content: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Asperiores neque blanditiis doloremque nisi tempora. Autem sapiente tempora facere veritatis. Sapiente ipsam deserunt eum corrupti, aliquam iure! Voluptate esse facere corrupti." },
      ]
    }
  },
  methods: {
    sortBy(prop){
      this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
    }
  }
}
</script>

<style>
.project.complete{
  border-left: 4px solid #3cd1c2;
}
.project.ongoing{
  border-left: 4px solid orange;
}
.project.overdue{
  border-left: 4px solid tomato;
}
.v-chip.complete{
  background: #3cd1c2;
}
.v-chip.ongoing{
  background: #ffaa2c;
}
.v-chip.overdue{
  background: #f83e70;
}
</style>
