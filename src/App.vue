<template>
  <div id="main">
    <div class="container">
    <div class="placeholder"></div>
      <div class="content">
      <section class="brand">
        <h1 class="title">
          Hello, I'm
          <span class="name">Moren YANG</span>
        </h1>
        <p class="subtitle">{{subtitle}}</p>
      </section>
      <section class="links">
        <div class="link" v-for="link in links">
          <a :href="link.href">{{link.name}}</a><span v-if="link.sub" class="link-sub">{{link.sub}}</span>
        </div>
      </section>
      </div>
    </div>
  </div>
</template>

<script>
import './assets/stylesheets/bootstrap.min.css'
import './assets/stylesheets/fonts.css'

export default {
  name: 'app',
  data(){
    return{
      subtitle: 'Front-end programmer, major in Software Engineering. ',
      links:[
        {
          name: 'Blog',
          href: '/blog',
          sub: 'code, inspiration & experience',
        },
        {
          name: 'GitHub',
          href: 'https://github.com/morenyang',
          sub: 'embrace the open source world'
        },
        {
          name: 'Instagram',
          href: 'https://www.instagram.com/morenyang/',
          sub: 'photos & daily'
        },
        {
          name: 'Lofter',
          href: 'http://morenyang.lofter.com/',
          sub: 'photographs & design'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
color =  #333
oxygen = 'Oxygen', 'Roboto', 'Avenir', Helvetica, Arial, sans-serif;
roboto = 'Roboto', 'Avenir', Helvetica, Arial, sans-serif;

#app {
  min-height 100vh
  font-family: roboto
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.placeholder{
  margin-top: 24vh
}

.content{
  section{
    margin-bottom: 50px
    @media screen and (max-width 767px){
      margin-bottom: 20px
    }
  }
  .brand{
    .title{
    font-weight: 300;
    font-family: oxygen
    font-size: 36px;
    @media screen and (max-width 767px){
      font-size: 20px
    }
      .name{
        font-size: 56px
        @media screen and (max-width 767px){
          font-size: 32px
        }
      }
    }
    .subtitle{
      font-size: 28px
      font-weight: 300
        @media screen and (max-width 767px){
          font-size: 18px
        }
    }
  }
  .links{
    .link{
      font-weight 300
      font-family oxygen
      color: color
      font-size: 24px
      line-height: 30px
      display: block
      @media screen and (max-width 767px){
        font-size: 18px
      }
      a{
        color color
        transition all 0.2s ease-in-out 0s
        &:hover{
          text-decoration: none
          +.link-sub{
            color: #aaa
          }
        }
      }
      .link-sub{
          font-size: 20px
          font-family: roboto
          font-weight: 200
          margin-left: 15px
          color: rgba(0,0,0,0)
          transition all 0.2s ease-in-out 0s
          user-select: none !important
          -webkit-user-select: none !important
          -moz-user-select: none !important
          -ms-user-select: none !important
          cursor default
        }
    }
  }
}
</style>
