<script>
import mainUsers from '../data/mainUsers';
import Card from './Card.vue';

export default {
  name: 'Main',
  components:{
    Card
  },
  data(){
    return{
      mainUsers
    }
  }
}
</script>

<template>
  <main>
    <div class="container">
      <div class="row">
        <Card
          v-for="user in mainUsers"
          :key="user.id"
          :user="user" />
      </div>
    </div>
  </main>
</template>

<style lang="scss">
  @use '../scss/partials/variables' as *;
  
  .row{
    display: flex;
    flex-wrap: wrap;
    width: $h-100;
    margin-top: 50px;
  }
</style>