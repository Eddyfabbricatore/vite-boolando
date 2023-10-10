<script>
import headerCategorysMenu from '../data/headerCategorysMenu';
import headerIconsMenu from '../data/headerIconsMenu';

export default {
  name: 'Header',
  data(){
    return{
      headerCategorysMenu,

      imgSrc: 'boolean-logo.png',

      headerIconsMenu
    }
  },

  methods:{
    getImgSrc(img){
      return new URL(`../assets/img/${img}`, import.meta.url).href;
    }
  }
}
</script>

<template>
  <header>
    <div class="container">
      <nav>
        <ul>
          <li v-for="(item, index) in headerCategorysMenu" :key="index">
            <a :href="item.href">{{ item.text }}</a>
          </li>
        </ul>
      </nav>

      <div class="logo">
        <img :src="getImgSrc(imgSrc)" alt="Logo">
      </div>

      <nav>
        <ul>
          <li v-for="(item, index) in headerIconsMenu" :key="index">
            <a :href="item.href"><i :class="item.text"></i></a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style lang="scss" scoped>
  @use '../scss/partials/variables' as *;

  header{
    height: $h-header;
    background-color: $bg-header;

    .container{
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: $h-100;

      li{
        margin: 0 10px;

        a{

          &:hover{
            text-decoration: underline;
          }
        }

        a,
        i{
          color: $color-link;
        }
      }

      .logo{
        width: $w-logo;
      }
    }
  }
</style>