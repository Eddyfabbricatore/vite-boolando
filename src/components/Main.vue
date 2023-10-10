<script>
export default {
  name: 'Main',
  data(){
    return{
      users: [
        {
          imgSrc: '1.webp',
          imgHideSrc: '1b.webp',
          iconHeart: 'fa-solid fa-heart',
          discount: '-50%',
          sustainability: 'sostenibilità',
          brand: 'levi\'s',
          nameProduct: 'relaxed fit tee unisex',
          priceDiscounted: '14,99 €',
          priceFull: '29,99 €'
        },

        {
          imgSrc: '2.webp',
          imgHideSrc: '2b.webp',
          iconHeart: 'fa-solid fa-heart',
          discount: '-30%',
          sustainability: '',
          brand: 'guess',
          nameProduct: 'roses tee',
          priceDiscounted: '20,99 €',
          priceFull: '29,99 €'
        },

        {
          imgSrc: '3.webp',
          imgHideSrc: '3b.webp',
          iconHeart: 'fa-solid fa-heart',
          discount: '-30%',
          sustainability: '',
          brand: 'come zucchero filato',
          nameProduct: 'voglia di colori pastello',
          priceDiscounted: '129,99 €',
          priceFull: '184,99 €'
        },

        {
          imgSrc: '4.webp',
          imgHideSrc: '4b.webp',
          iconHeart: 'fa-solid fa-heart',
          discount: '-50%',
          sustainability: 'sostenibilità',
          brand: 'levi\'s',
          nameProduct: 'tee unisex',
          priceDiscounted: '14,99 €',
          priceFull: '29,99 €'
        },

        {
          imgSrc: '5.webp',
          imgHideSrc: '5b.webp',
          iconHeart: 'fa-solid fa-heart',
          discount: '',
          sustainability: '',
          brand: 'maya deluxe',
          nameProduct: 'stripe bodice',
          priceDiscounted: '99,99 €',
          priceFull: ''
        },

        {
          imgSrc: '6.webp',
          imgHideSrc: '6b.webp',
          iconHeart: 'fa-solid fa-heart',
          discount: '',
          sustainability: 'sostenibilità',
          brand: 'esprit',
          nameProduct: 'maglione - black',
          priceDiscounted: '29,99 €',
          priceFull: ''
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
  <main>
    <div class="container">
      <div class="row">
        <!-- card  -->
        <div class="col" v-for="(user, index) in users" :key="index">
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