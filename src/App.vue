<template>
  <div class="landing">
    <header>
      <div class="landing_nav">
        <h1 class="landing_logo"><a href="#"></a></h1>
        <nav>
          <Popup v-show="showPopup" class="landing_mobile_nav"></Popup>
          <ul class="landing_desktop_nav">
            <li></li>
          </ul>
        </nav>
        <button class="landing_show_nav" @click="showPopup=true">open nav</button>
      </div>
      <h2>IMMERSIVE EXPERIENCES THAT DELIVER</h2>
    </header>
    <main>
      <article class="landing_intro">
        <img class="landing_intro_img" src="./assets/images/mobile/image-interactive.jpg" alt="">
        <h3 class="landing_intro_title">THE LEADER IN INTERACTIVE VR</h3>
        <p class="landing_intro_msg">
          Founded in 2011, Loopstudios has been producing world-class virtual reality
          projects for some of the best companies around the globe. Our award-winning
          creations have transformed businesses through digital experiences that bind
          to their brand.
        </p>
      </article>
      <section class="landing_creations">
        <h3 class="landing_creations_title">OUR CREATIONS</h3>
        <ul class="landing_creations_card">
          <li
          v-for="(item, index) in creationCard"
          :key="index"
          >
            <div class="landing_creations_img"><img :src="item.image" alt=""></div>
            <p class="landing_creations_card_des">{{item.line1}}<br>{{item.line2}}</p>
          </li>
        </ul>
        <button class="landing_creations_all">SEE ALL</button>
      </section>
    </main>
    <footer>
      <div class="landing_company_left">
        <h4 class="landing_company_logo"></h4>
        <ul class="landing_company">
          <li
          class="landing_company_item"
          v-for="(item, index) in companyList"
          :key="index"
          ><a href="#"></a>{{item}}</li>
        </ul>
      </div>
      <div class="landing_share_right">
        <ul>
          <li
            v-for="(item, index) in shareList"
            :key="index"
          >
            <a href="#">
              <img :src="item" alt="">
            </a>
          </li>
        </ul>
        <div class="landing_copyright">
          © 2021 Loopstudios. All rights reserved.
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import Popup from './components/Popup.vue'
export default {
  name: 'App',
  components: {
    Popup
  },
  data () {
    return {
      // our creations
      creationCard: [
        {
          image: require('./assets/images/mobile/image-deep-earth.jpg'),
          line1: 'DEEP',
          line2: 'EARTH'
        },
        {
          image: require('./assets/images/mobile/image-night-arcade.jpg'),
          line1: 'NIGHT',
          line2: 'ARCADE'
        },
        {
          image: require('./assets/images/mobile/image-soccer-team.jpg'),
          line1: 'SOCCER',
          line2: 'TEAM VR'
        },
        {
          image: require('./assets/images/mobile/image-grid.jpg'),
          line1: 'THE',
          line2: 'GRID'
        },
        {
          image: require('./assets/images/mobile/image-from-above.jpg'),
          line1: 'FROM UP',
          line2: 'ABOVE VR'
        },
        {
          image: require('./assets/images/mobile/image-pocket-borealis.jpg'),
          line1: 'POCKET',
          line2: 'BOREALIS'
        },
        {
          image: require('./assets/images/mobile/image-curiosity.jpg'),
          line1: 'THE',
          line2: 'CURIOSITY'
        },
        {
          image: require('./assets/images/mobile/image-fisheye.jpg'),
          line1: 'MAKE IT',
          line2: 'FISHEYE'
        }
      ],
      companyList: [
        'About', 'Careers', 'Events', 'Products', 'Support'
      ],
      shareList: [
        require('./assets/images/icon-facebook.svg'),
        require('./assets/images/icon-twitter.svg'),
        require('./assets/images/icon-pinterest.svg'),
        require('./assets/images/icon-instagram.svg')
      ],
      showPopup: false
    }
  }
}
</script>

<style lang="less">
@import './styles/index.less';
</style>
