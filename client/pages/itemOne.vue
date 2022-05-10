<template>
  <div>
    <h2 style="width: 100%; margin: 10px auto; text-align: center">Кратные числа</h2>
    <br />
    <br />
    <span>Результат: {{a}}</span>
    <br />
    <br />
    <v-btn @click="showList = !showList"> {{ showList ? 'Скрыть числа' : 'Показать числа' }} </v-btn>
    <br />
    <br />

    <div v-show="showList">
      {{ itemList }}
    </div>
<!--    Или же -->
<!--    <div v-show="showList">-->
<!--      <div v-for="item in itemList" style="display: flex; flex-direction: row;">-->
<!--        <span>{{item}}</span>-->
<!--      </div>-->
<!--    </div>-->
  </div>
</template>

<script lang="ts">
import {Component, Vue} from "vue-property-decorator"
@Component
export default class ItemOne extends Vue {
  private items:number = 1000
  private itemList:any = []
  private showList:boolean = false;
  private i:number = 0
  private a:number = 0

  created () {
    do {
      this.i++
      if (this.i % 3 == 0 || this.i % 5 == 0) {
        if (this.i > this.items) {return} else {
          this.a = this.a + this.i
          this.itemList.push (this.i)
        }
      }
    } while (this.i <= this.items)
  }

}
</script>

<style></style>
