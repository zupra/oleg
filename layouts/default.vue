<template lang="pug">
div
  //- <nuxt />


  #CrossFade
    each img in ['https://manceraparfums.com/themes/mancera2016/img/wild_python_mid1.jpg','https://manceraparfums.com/themes/mancera2016/img/home_roses_vanille_small.jpg','https://manceraparfums.com/themes/mancera2016/img/home_black_gold_medium.jpg']
      img(src=''+img, alt="img")

    .intro.bold
      h1.bold
        span С днем рождения дружище !!!
      h4.bold
        span
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Perferendis impedit facilis nesciunt quam vitae voluptatibus ullam vero.

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





  #footer
    #footer-wrap

      .flex.x_sb
        form.mr-5(ref="ftr_form")
          input.mb-2(type="text", name="entry.1694504546", placeholder="* Телефон")
          textarea(name="entry.1527676226", placeholder="Сообщение")
          button.btn(@click.prevent="submit()") Отправить

        div
          h4 Eсть вопросы или предложения?
          p Оставьте сообщение которое сразу придёт нам в SMS. Если это важно или интересно — мы оперативно ответим.
          h4 Пообщаемся в СоцСетях?
          .Socials-set
            a(href="//vk.com/#")
              svg.icon
                use(xmlns:xlink='http://www.w3.org/1999/xlink', xlink:href='#icon_vk')
              //| vkontakte
            a(href="//facebook.com/#")
              svg.icon
                use(xmlns:xlink='http://www.w3.org/1999/xlink', xlink:href='#icon_fb')
              //| facebook
            a(href="//instagram.com/#")
              svg.icon
                use(xmlns:xlink='http://www.w3.org/1999/xlink', xlink:href='#icon_instagram')
              //| instagram
      .flex.x_sb
        .nav
          h4 OOO «
            b ВИНСТОН
            |»
          | г. Москва, Покровка 3/7
          br
          | тел.: +7(495) 64-255-64
          br
          | режим работы: Пн-Пт
          br
          | с 10-20 часов
          br
          | Сб-Вс - выходной
        nav
          h4 Инфо
          nuxt-link(to="/#") О компании
          a(href="/#") Обмен и возврат
          nuxt-link(to="/#") Отзывы
          nuxt-link(to="/contacts") Контакты
          nuxt-link(to="/cooperation") Сотрудничество
          a(href="#") Узнать статус заказа
          // a(href="#") Контакты
          // a(href="#") Отзывы о ремонте
          // a(href="#") Сотрудничество
        div
          nav.Socials-set
            h4 Поделиться
            a(href="/#")
              svg.icon
                use(xmlns:xlink='http://www.w3.org/1999/xlink', xlink:href='#icon_twitter')
              | share twitter
            a(href="/#")
              svg.icon
                use(xmlns:xlink='http://www.w3.org/1999/xlink', xlink:href='#icon_vk')
              | share vkontakte
            a(href="/#")
              svg.icon
                use(xmlns:xlink='http://www.w3.org/1999/xlink', xlink:href='#icon_fb')
              | share facebook
            a(href="/#")
              svg.icon
                use(xmlns:xlink='http://www.w3.org/1999/xlink', xlink:href='#icon_googleplus')
              | share Gplus
            a(href="/#")
              svg.icon
                use(xmlns:xlink='http://www.w3.org/1999/xlink', xlink:href='#icon_ok')
              | share odnoklassniki


  <SocIcon/>




</template>



<script>
import SocIcon from '~/components/SocIcon.vue';
export default {

  components: {
    SocIcon
  },
  data () {
    return {
    }
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



#footer
  //background-image: linear-gradient( 135deg, #FFCF71 10%, #2376DD 100%);
  background-image: linear-gradient( 135deg, #FD6585 10%, #0D25B9 100%);
  padding: 3em 0

  color #EEE

  h2, h4, h4
    /* font-weight normal */
    color #FFF


  nav, .nav
    margin 2em 1em
    a
      color #cddc39 //$text
      //text-decoration: $header underline

      display: block
      //line-height 2em
      &:hover
        color #FFF

  /* input, textarea
    &:focus
      background: #000;
      color #FFF */

#footer-wrap
  max-width: 1080px;
  margin: auto;
  padding: 0 1em;



.Socials-set
  a
    white-space nowrap
    &:hover .icon
      //background: $header + 20
      //background: $text
      background: rgba(#000 .45)
  .icon
    border-radius 3px
    vertical-align: middle;
    width: 16px
    height 16px
    padding: 10px
    box-sizing: content-box
    margin 4px
    fill: #FFF
    background: rgba(#EEE .2)//$header




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
      animation-delay 2s
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

  position relative
  margin 2em
  padding .2em .6em
  cursor pointer
  max-width: 50%

  span
    /* padding: 0 .3em; */
    /* background: #e91e63 */
    background: rgba(107,170,184,0.3);


</style>
