<script>
import footerInfos from '../data/footerInfos';
import footerLinks from '../data/footerLinks';

export default {
  name: 'Footer',
  data(){
    return{
      infoTitle: 'boolando s.r.l',

      footerInfos,

      linkTitle: 'Trovaci anche su',

      footerLinks
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
            <li v-for="(info, index) in footerInfos" :key="index">
              <a href="info.href">{{ info.text }}</a>
            </li>
          </ul>
        </nav>
      </div>

      <div class="link">
        <h3>{{ linkTitle }}</h3>

        <nav>
          <ul>
            <li v-for="(link, index) in footerLinks" :key="index">
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