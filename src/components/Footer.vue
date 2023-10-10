<script>
export default {
  name: 'Footer',
  data(){
    return{
      infoTitle: 'boolando s.r.l',

      infos: [
        {
          href: '#',
          text: 'informazioni legali'
        },

        {
          href: '#',
          text: 'informazioni sulla privacy'
        },

        {
          href: '#',
          text: 'diritto di recesso'
        }
      ],

      linkTitle: 'Trovaci anche su',

      links: [
        {
          href: '#',
          icon: 'fa-brands fa-square-twitter'
        },

        {
          href: '#',
          icon: 'fa-brands fa-square-facebook'
        },

        {
          href: '#',
          icon: 'fa-brands fa-square-instagram'
        },

        {
          href: '#',
          icon: 'fa-brands fa-square-pinterest'
        },

        {
          href: '#',
          icon: 'fa-brands fa-square-youtube'
        }
      ]
    }
  }
}
</script>

<template>
  <footer>
    <div class="container">
      <div class="info">
        <h3>{{ infoTitle }}</h3>

        <nav>
          <ul>
            <li v-for="(info, index) in infos" :key="index">
              <a href="info.href">{{ info.text }}</a>
            </li>
          </ul>
        </nav>
      </div>

      <div class="link">
        <h3>{{ linkTitle }}</h3>

        <nav>
          <ul>
            <li v-for="(link, index) in links" :key="index">
              <a href="link.href"><i :class="link.icon"></i></a>
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
  @use '../scss/partials/variables' as *;

  footer{
    height: $h-footer;
    background-color: $bg-footer;

    .container{
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: $h-100;

      .info{
        h3{
          margin-left: 10px;
          text-transform: capitalize;
        }

        li{
          margin: 0 5px;

          &:first-of-type{
            margin-left: 10px;
          }
  
          &:hover{
            text-decoration: underline;
          }
        }
      }

      .link{
        margin-right: 10px;

        ul{
          display: flex;
          justify-content: space-between;
        }
      }

      .info,
      .link,
      a{
        color: $color-link;
      }

      .info,
      .link{
        display: flex;
        flex-direction: column;
      }

      h3{
        margin-bottom: 10px;
      }

      ul{
        list-style: none;

        li{
          display: inline-block;
          text-transform: capitalize;

          a{
            text-decoration: none;
          }
        }
      }
    }

  }
</style>