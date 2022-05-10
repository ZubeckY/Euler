<template>
  <v-container>
    <h2 style="width: 100%; text-align: center; margin: 20px 0; ">Задачи по Эйлеру</h2>
    <v-row>
      <v-col style="height: 600px; overflow-y: auto;">
        <div v-for="(item, i) in leng">
          <v-card style="margin: 10px; padding: 10px">
            <v-row>
              <v-col class="col-auto d-flex"> {{i+1}} </v-col>
              <v-col><v-btn text width="100%" @click='GLink = item.link'> {{item.title}} </v-btn></v-col>
            </v-row>
          </v-card>
        </div>
      </v-col>
      <v-col>
        <iframe :src=GLink style="width: 100%; height: 500px;"></iframe>
      </v-col>
    </v-row>
  </v-container>
</template>
<script lang="ts">
import {Component, Vue} from "vue-property-decorator"
@Component
export default class Index extends Vue {

  private GLink:any = ''
  private leng:any = [
    {
      title: 'any',
      link: '/itemOne',
    },
    {
      title: 'any',
      link: '/itemTwo',
    },
  ]



  created () {

  }

}
</script>
<style>
  .container { max-width: 1200px;}

</style>
