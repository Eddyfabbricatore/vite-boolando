<script>
export default {
  name: 'Header',
  data(){
    return{
      categoryMenu: [
        {
          href: '#',
          text: 'uomo'
        },

        {
          href: '#',
          text: 'donna'
        },

        {
          href: '#',
          text: 'bambini'
        }
      ],

      imgSrc: 'boolean-logo.png',

      iconMenu: [
        {
          href: '#',
          text: 'fa-regular fa-user'
        },

        {
          href: '#',
          text: 'fa-regular fa-heart'
        },

        {
          href: '#',
          text: 'fa-solid fa-bag-shopping'
        }
      ]
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
          <li v-for="(item, index) in categoryMenu" :key="index">
            <a :href="item.href">{{ item.text }}</a>
          </li>
        </ul>
      </nav>

      <div class="logo">
        <img :src="getImgSrc(imgSrc)" alt="Logo">
      </div>

      <nav>
        <ul>
          <li v-for="(item, index) in iconMenu" :key="index">
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