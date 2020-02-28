<template lang="pug">
div
  //- <nuxt />


  #CrossFade
    each img in ['https://obj.altapress.ru/picture/555164/936x530.jpg','https://ratatum.com/wp-content/uploads/2018/05/47417-2.jpg','https://manceraparfums.com/themes/mancera2016/img/wild_python_mid1.jpg','https://manceraparfums.com/themes/mancera2016/img/home_roses_vanille_small.jpg','https://manceraparfums.com/themes/mancera2016/img/home_black_gold_medium.jpg']
      img(src=''+img, alt="img")

    .intro.bold
      h1.bold
        span.sp1 Оригинальная 
          br 
          | парфюмерия из Франции
      h3
        span.sp2 Ароматы, они как страницы из личного дневника. 
          br
          | C его тайнами и мыслями.
  #grid
    -for(i=1;i<5;i++)
      .mask(class='col_'+i)
    -for(i=1;i<7;i++)
      .mask(class='row_'+i)
    .txt.txt_1
      h1.bold Здесь будет сетка каталога
      br
      p Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam, nihil quae recusandae minima eveniet officia a. Non animi necessitatibus eos consequuntur et sunt nulla libero. Aliquid provident numquam ex soluta?
    .txt.txt_2.bold
      p
        span Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam, nihil quae recusandae minima eveniet officia a. Non animi necessitatibus eos consequuntur et sunt nulla libero. Aliquid provident numquam ex soluta?
      p
        span Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam, nihil quae recusandae minima eveniet officia a. Non animi necessitatibus eos consequuntur et sunt nulla libero. Aliquid provident numquam ex soluta?
      p
        span Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam, nihil quae recusandae minima eveniet officia a. Non animi necessitatibus eos consequuntur et sunt nulla libero. Aliquid provident numquam ex soluta?

    h2.txt.txt_3
      i Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam, nihil quae recusandae minima eveniet officia a. Non animi necessitatibus eos consequuntur et sunt nulla libero. Aliquid provident numquam ex soluta?

    img(src="https://manceraparfums.com/themes/mancera2016/img/home_hair_mist_small.jpg", alt="")

  <Footer/>

</template>



<script>
import Footer from '~/components/Footer.vue'
export default {
  components: {
    Footer
  },
  data() {
    return {}
  }
}
</script>

<style lang="styl">


#grid
  color #222
  margin 3em auto
  width 82%
  max-width 1200px

  display grid
  grid-template-columns repeat(4, 1fr)
  //grid-template-rows repeat(6, 12vw)
  //grid-auto-rows minmax(12vw, auto);
  grid-template-rows repeat(6, minmax(12vw, auto))
  grid-gap 2vw

.mask
  border 1px solid #CCC
  // z-index -1
  /* &:hover
    background #000 */
for num in 1..4
  .col_{num}
    grid-row 1 / 7
    grid-column num / num+1
for num in 1..6
  .row_{num}
    grid-column 1 / 5
    grid-row num / num+1

.txt
  padding 1rem
.txt_1
  // text-align center
  grid-row 1 / 2
  grid-column 1 / 4
  background #FFF //rgba(red, .2)
  margin-left -2vw
  border: 2px solid #111;
  box-shadow: 1vw 1vw #FFED00;

.txt_2
  //align-self center
  margin auto
  grid-row 2 / 5
  grid-column 1 / 3
  background rgba(#e91e63, .1)
  position relative
  // top 1vw
  left 2vw
  // margin-right 8em
  span
    background #FFED00 //gold


.txt_3
  // align-self end
  grid-row 5 / 6
  grid-column 1 / 3

  box-shadow: 1rem 1rem #00bcd4;
  transform: scale(.7)
  color cornsilk
  padding 1rem
  background rgba(#6BAAB8, .7)
  i
    background #960000


img
  /* border 2px solid rgba(244, 68, 46, 0.5); */
  //z-index -1
  object-fit cover
  //overflow hidden
  width 100%
  height 100%
  box-shadow: 0 2px 1em #bbb, 0 2px 1em #000, 10px 10px 0 0 rgba(#FFED00, 0.6);

  grid-row 2 / 6
  grid-column 3 / 5









#CrossFade
  color #FFF
  background #000 //no flash

  display flex
  align-items flex-end

  height 100vh
  overflow hidden
  position relative

  img
    position absolute
    min-width 100%
    min-height 100%
    height auto
    background #000


    backface-visibility hidden
    opacity 0
    transform scale(1.4) rotate(12deg)

    animation CrossFade 24s infinite
    &:nth-child(3)
      animation-delay 6s
    &:nth-child(2)
      animation-delay 12s
    &:nth-child(1)
      animation-delay 18s

@keyframes CrossFade
  25%
    opacity 1
    transform scale(1) rotate(0)
  40%
    opacity 0




.intro


  user-select: none;

  position relative
  margin 2em
  margin-left: 5em;
  padding .2em .6em
  cursor pointer
  /* max-width: 600px */



  &:before
    content ''
    position absolute
    top -30px
    left -50px
    width 100px
    height 100px
    border solid 4px #ffed00 //rgba(#ffed00, .6)
    clip-path polygon(0 0, 0 110px, 40px 110px, 40px 10px, 110px 20px, 110px 0)


  .sp1
    /* padding: 0 .3em; */
    /* background: #e91e63 */
    background: #ffed0099 // rgba(107,170,184,0.3);
    /* background rgba(#fd658569,.5) */


  .sp2
    background rgba(#000,.5)

</style>
