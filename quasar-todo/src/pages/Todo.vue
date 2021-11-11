<template>
  <q-page class="bg-grey-3 column">
   <q-list 
   class="bg-white"
   separator
   bordered>
      <q-item
      v-for="task in tasks" 
      :key="task.tittle" 
      @click="task.done = !task.done"
      :class="{'done bg-blue-1' : task.done}"
      clickable
      v-ripple>
        <q-item-section avatar>
          <q-checkbox 
          v-model="task.done"
          class="no-pointer-events"
            color="primary" />
        </q-item-section>
        <q-item-section>
          <q-item-label>{{task.tittle}}</q-item-label>
        </q-item-section>
      </q-item>
      </q-list>
  </q-page>
</template>

<script>

export default {
  data(){
    return{
      tasks: [
        {
          tittle: 'Get bananas',
          done: false
        },
        {
           tittle: 'Eat bananas',
          done: false
        },
        {
           tittle: 'Poo bananas',
          done: false
        }
      ]

    }
  }
 
}
</script>
<style lang="scss">
.done{
  .q-item__label{
    text-decoration: line-through ;
    color: gray;
  }
}

</style>
