<script>
export default {
  name: 'Footer'
}
</script>

<template>
  <footer>
    <div class="container">
      <div class="info">
        <h3>boolando s.r.l</h3>

        <nav>
          <ul>
            <li>
              <a href="#">informazioni legali</a>
            </li>

            <li>
              <a href="#">informazioni sulla privacy</a>
            </li>

            <li>
              <a href="#">diritto di recesso</a>
            </li>
          </ul>
        </nav>
      </div>

      <div class="link">
        <h3>Trovaci anche su</h3>

        <nav>
          <ul>
            <li>
              <a href="#"><i class="fa-brands fa-square-twitter"></i></a>
            </li>

            <li>
              <a href="#"><i class="fa-brands fa-square-facebook"></i></a>
            </li>

            <li>
              <a href="#"><i class="fa-brands fa-square-instagram"></i></a>
            </li>

            <li>
              <a href="#"><i class="fa-brands fa-square-pinterest"></i></a>
            </li>

            <li>
              <a href="#"><i class="fa-brands fa-square-youtube"></i></a>
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