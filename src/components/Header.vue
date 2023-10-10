<script>
export default {
  name: 'Header'
}
</script>

<template>
  <header>
    <div class="container">
      <nav>
        <ul>
          <li><a href="#">uomo</a></li>
          <li><a href="#">donna</a></li>
          <li><a href="#">bambini</a></li>
        </ul>
      </nav>

      <div class="logo">
        <img src="../assets/img/boolean-logo.png" alt="Logo">
      </div>

      <nav>
        <ul>
          <li><a href="#"><i class="fa-regular fa-user"></i></a></li>
          <li><a href="#"><i class="fa-regular fa-heart"></i></a></li>
          <li><a href="#"><i class="fa-solid fa-bag-shopping"></i></a></li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style lang="scss" scoped>
  @use '../scss/partials/variables' as *;

  header{
    height: $ht-header;
    background-color: $bg-header;

    .container{
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 100%;

      li{
        display: inline-block;
        margin: 0 10px;
        text-transform: capitalize;

        a{
          text-decoration: none;

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
        width: 100px;
      }
    }
  }
</style>