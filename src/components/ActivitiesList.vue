<template>
  <v-flex xs12 sm6 offset-sm3>
    <v-card>
      <v-toolbar color="cyan">
        <v-toolbar-title>Todo List</v-toolbar-title>
      </v-toolbar>
      <v-card-text>
        <AddActivityField/>
        <v-list subheader>
          <Activity v-for="(activity, index) in activities" :key="index" :activity="activity" />
        </v-list>
      </v-card-text>
    </v-card>
  </v-flex>
</template>

<script lang="ts">
import Activity from './Activity.vue'
import AddActivityField from './AddActivityField.vue'
import { Component, Vue } from 'vue-property-decorator'

@Component({
  components: {
    Activity,
    AddActivityField
  }
})
class ActivitiesList extends Vue {
  get activities (): Object {
    return this.$store.state.activities
  }
}
export default ActivitiesList
</script>

<style>
</style>
