<script>
import mainUsers from '../data/mainUsers';

export default {
  name: 'Main',
  data(){
    return{
      mainUsers
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
  <main>
    <div class="container">
      <div class="row">
        <!-- card  -->
        <div class="col" v-for="(user, index) in mainUsers" :key="index">
          <div class="card">
            <div class="card-image">
              <div class="image">
                <img :src="getImgSrc(user.imgSrc)" alt="nome prodotto...">

                <img class="hide" :src="getImgSrc(user.imgHideSrc)" alt="nome prodotto...">
              </div>

              <div class="heart"><i :class="user.iconHeart"></i></div>

              <div class="card-badge">
                <span class="discount" v-if="user.discount.length > 0">{{ user.discount }}</span>

                <span class="sustainability" v-if="user.sustainability.length > 0">{{ user.sustainability }}</span>
              </div>
            </div>

            <div class="card-text">
              <span>{{ user.brand }}</span>

              <h3>{{ user.nameProduct }}</h3>

              <div class="price">
                <span v-if="user.priceDiscounted.length > 0">{{ user.priceDiscounted }}</span>

                <del v-if="user.priceFull.length > 0">{{ user.priceFull }}</del>
              </div>
            </div>
          </div> 
        </div>
        <!-- /card  -->
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
  @use '../scss/partials/variables' as *;

  .container{
    margin-top: 50px;
  }

  .row{
    display: flex;
    flex-wrap: wrap;
    width: $h-100;

    .col{
      width: $w-col;

      .card{
        margin-bottom: 40px;
        padding: 0 10px;

        .card-image{
          position: relative;

          .image{
            height: $h-card-image;

            .hide{
              display: none;
            }

            &:hover{
              img{
                display: none;
              }

              img.hide{
                display: block;
              }
            }
          }

          .heart{
            position: absolute;
            top: 10px;
            right: 0;
            padding: 10px;
            background-color: $bg-body;

            i{
              color: $color-heart;
            }

            &:hover{
              cursor: pointer;

              i{
                color: $bg-discount;
              }
            }
          }

          .card-badge{
            position: absolute;
            bottom: 30px;
            left: 0;

            .discount{
              margin-right: 10px;
              background-color: $bg-discount;
            }

            .sustainability{
              text-transform: capitalize;
              background-color: $bg-sustainability;
            }

            .discount,
            .sustainability{
              padding: 5px;
              color: $color-link;
            }
          }
        }

        .card-text{
          span{
            text-transform: capitalize;
          }

          h3{
            text-transform: uppercase;
          }

          .price{
            span{
              margin-right: 10px;
              color: $bg-discount;
            }
          }
        }
      }
    }
  }
</style>