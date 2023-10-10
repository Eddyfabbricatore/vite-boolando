<script>
export default {
  name: 'Main'
}
</script>

<template>
  <main>
    <div class="container">
      <div class="row">
        <!-- card  -->
        <div class="col">
          <div class="card">
            <div class="card-image">
              <div>
                <img src="../assets/img/1.webp" alt="nome prodotto...">

                <img class="hide" src="../assets/img/1b.webp" alt="nome prodotto...">
              </div>

              <div class="heart"><i class="fa-solid fa-heart"></i></div>

              <div class="card-badge">
                <span class="discount">-50%</span>

                <span class="sustainability">sostenibilità</span>
              </div>
            </div>

            <div class="card-text">
              <span>levi's</span>

              <h3>relaxed fit tee unisex</h3>

              <div class="price">
                <span>14,99 €</span>

                <del>29,99 €</del>
              </div>
            </div>
          </div> 
        </div>
        <!-- /card  -->

        <!-- card  -->
        <div class="col">
          <div class="card">
            <div class="card-image">
              <div>
                <img src="../assets/img/2.webp" alt="nome prodotto...">

                <img class="hide" src="../assets/img/2b.webp" alt="nome prodotto...">
              </div>

              <div class="heart"><i class="fa-solid fa-heart"></i></div>

              <div class="card-badge">
                <span class="discount">-30%</span>
              </div>
            </div>

            <div class="card-text">
              <span>guess</span>
              <h3>roses tee</h3>

              <div class="price">
                <span>20,99 €</span>

                <del>29,99 €</del>
              </div>
            </div>
          </div> 
        </div>
        <!-- /card  -->

        <!-- card  -->
        <div class="col">
          <div class="card">
            <div class="card-image">
              <div>
                <img src="../assets/img/3.webp" alt="nome prodotto...">

                <img class="hide" src="../assets/img/3b.webp" alt="nome prodotto...">
              </div>

              <div class="heart"><i class="fa-solid fa-heart"></i></div>

              <div class="card-badge">
                <span class="discount">-30%</span>
              </div>
            </div>

            <div class="card-text">
              <span>come zucchero filato</span>

              <h3>voglia di colori pastello</h3>

              <div class="price">
                <span>129,99 €</span>

                <del>184,99 €</del>
              </div>
            </div>
          </div> 
        </div>
        <!-- /card  -->

        <!-- card  -->
        <div class="col">
          <div class="card">
            <div class="card-image">
              <div>
                <img src="../assets/img/4.webp" alt="nome prodotto...">

                <img class="hide" src="../assets/img/4b.webp" alt="nome prodotto...">
              </div>

              <div class="heart"><i class="fa-solid fa-heart"></i></div>

              <div class="card-badge">
                <span class="discount">-50%</span>

                <span class="sustainability">sostenibilità</span>
              </div>
            </div>

            <div class="card-text">
              <span>levi's</span>

              <h3>tee unisex</h3>

              <div class="price">
                <span>14,99 €</span>

                <del>29,99 €</del>
              </div>
            </div>
          </div> 
        </div>
        <!-- /card  -->

        <!-- card  -->
        <div class="col">
          <div class="card">
            <div class="card-image">
              <div>
                <img src="../assets/img/5.webp" alt="nome prodotto...">
                
                <img class="hide" src="../assets/img/5b.webp" alt="nome prodotto...">
              </div>

              <div class="heart"><i class="fa-solid fa-heart"></i></div>
            </div>

            <div class="card-text">
              <span>maya deluxe</span>

              <h3>stripe bodice</h3>

              <div class="price">
                <span>99,99 €</span>
              </div>
            </div>
          </div> 
        </div>
        <!-- /card  -->

        <!-- card  -->
        <div class="col">
          <div class="card">
            <div class="card-image">
              <div>
                <img src="../assets/img/6.webp" alt="nome prodotto...">
                <img class="hide" src="../assets/img/6b.webp" alt="nome prodotto...">
              </div>

              <div class="heart"><i class="fa-solid fa-heart"></i></div>

              <div class="card-badge">
                <span class="sustainability">sostenibilità</span>
              </div>
            </div>

            <div class="card-text">
              <span>esprit</span>

              <h3>maglione - black</h3>

              <div class="price">
                <span>29,99 €</span>
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
    width: 100%; 

    .col{
      width: calc(100% / 3);

      .card{
        margin-bottom: 40px;
        padding: 0 10px;

        .card-image{
          position: relative;

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
              background-color: $bg-discount;
            }

            .sustainability{
              margin-left: 10px;
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
              color: $bg-discount;
            }

            del{
              margin-left: 10px;
            }
          }
        }
      }
    }
  }
</style>