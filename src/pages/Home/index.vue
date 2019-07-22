<script>
  // @ is an alias to /src
  import TripStartContainer from '@/containers/TripStartContainer'
  import SocialMediaGroup from '@/components/SocialMediaGroup'
/* eslint-disable */
  export default {
    name: 'home',
    data() {
      return {
        scrollTop: 0,
        wh: 0,
        section1Class: false,
        section2Class: false,
        section3Class: false
      }
    },
    components: {
       TripStartContainer,
       SocialMediaGroup 
    },
    // computed: {
    //   windowHeight(){
    //     return window.innerHeight
    //   }
    // },
    methods: {  
      section1() {
        let obj = this.getOffset(document.querySelector('.section1'))
        return obj.top
      },
      section2() {
        let obj = this.getOffset(document.querySelector('.section2'))
        return obj.top
      },
      section3() {
        let obj = this.getOffset(document.querySelector('.section3'))
        return obj.top
      },
      getOffset(DOM) {
        let left = 0
        let top = 0
        if (DOM && DOM.offsetParent) {
          do {
            left += DOM.offsetLeft
            top += DOM.offsetTop
          } while ((DOM = DOM.offsetParent))
          return { top, left }
        }
        return { top, left }
      },
      scrollHandler() {
        this.scrollTop = document.querySelector('body').scrollTop || document.querySelector('html').scrollTop
        this.wh = window.innerHeight
        this.addAnimationClass()


      },
      addAnimationClass(){

        if(this.wh + this.scrollTop > this.section1()){
          this.section1Class = true
        }
        if(this.wh + this.scrollTop > this.section2()){
          this.section2Class = true
        }
        if(this.wh + this.scrollTop > this.section3()){
          this.section3Class = true
        }
      }
    },
    mounted() {
      document.addEventListener('scroll', this.scrollHandler)
    }
  }
</script>
<template src="./template.html"></template>
<style lang="scss" src="./style.scss" scoped />
