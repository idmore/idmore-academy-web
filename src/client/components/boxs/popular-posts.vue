<template lang="pug">
  .popular-post
    .container 
      .grid(v-if="data.status && data.status === 200")

        // 1
        card-large(:data="data.result[0]")
        
        // 2
        card-small(:data="data.result[1]")
        
        // 3
        card-small(:data="data.result[2]")
        
        // 4
        card-large(:data="data.result[3]")
        
        // 5
        card-small(:data="data.result[4]")

        // 6
        card-small(:data="data.result[5]")

        // 7
        card-small(:data="data.result[6]")

      .popular-end
          strong Idmore Academy 
          br 
          | More things available
</template>

<script lang="ts">
import Vue from "vue"
import CardSmall from "../cards/post-small.vue"
import CardLarge from "../cards/post-large.vue"

Vue.component("card-small", CardSmall)
Vue.component("card-large", CardLarge)

export default Vue.extend({
  name: "popular-post-box",

  props: ["data"]
})
</script>

<style lang="sass">
  @import '../../../design/sass/color'
  .popular-post 
    background-color: #FFF
    padding-top: 2em
    .container
      border: 3px solid $color-blue-main
  .card-post-popular 
      padding: 0
      color: $color-gray-medium
      text-transform: uppercase
      font-weight: 800
      transition: all .5s ease
      &:hover
        background: $color-blue-main
        color: $color-white-main
        box-shadow: 5px 5px 10px #175580;
        z-index: 2;
        a 
          color: $color-white-main
      a 
        color: $color-gray-medium
        font-size: 1.5em
      .thumb
        padding: 0
        .thumb-image 
          background-size: cover
      .title
        h2 
          margin: 0
        padding: 1em
        small, small a 
          font-size: 1em
      &.col-4_sm-12
        .thumb
          height: 220px
          .thumb-image 
            height: 100%
        .title 
          padding: .5em 
          h2, a 
            font-size: 1em
      &.col-8_sm-12
        .thumb-image
          height: 320px

  // popular-end style
  .popular-end 
    background-color: $color-blue-main
    color: $color-white-main 
    text-align: center 
    font-size: 1.3em 
    text-transform: uppercase
    padding: 2em 0

  // responsive
  @media screen and (max-width: 600px)
    .card-post-popular
      &.col-8_sm-12 
        h2
          font-size: .7em

</style>
