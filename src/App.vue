<template>
  <div class="landing">
    <header>
      <div class="landing_nav">
        <h1 class="landing_logo"><a href="#"></a></h1>
        <nav>
          <Popup v-model="showPopup" class="landing_mobile_nav">
            <ul>
              <li
                v-for="(item, index) in companyList"
                :key="index"
              ><a href="#">{{item}}</a></li>
            </ul>
          </Popup>
          <ul class="landing_desktop_nav">
            <li
              v-for="(item, index) in companyList"
              :key="index"
            ><a href="#">{{item}}</a></li>
          </ul>
        </nav>
        <button class="landing_show_nav" @click="showPopup=true">open nav</button>
      </div>
      <h2>IMMERSIVE EXPERIENCES THAT DELIVER</h2>
    </header>
    <main>
      <article class="landing_intro">
        <div class="center">
          <img class="landing_intro_img" src="./assets/images/mobile/image-interactive.jpg" alt="">
          <div class="landing_intro_card">
            <h3 class="landing_intro_title">THE LEADER IN INTERACTIVE VR</h3>
            <p class="landing_intro_msg">
              Founded in 2011, Loopstudios has been producing world-class virtual reality
              projects for some of the best companies around the globe. Our award-winning
              creations have transformed businesses through digital experiences that bind
              to their brand.
            </p>
          </div>
        </div>
      </article>
      <section class="landing_creations">
        <h3 class="landing_creations_title">OUR CREATIONS</h3>
        <ul class="landing_creations_card_mobile">
          <li
          v-for="(item, index) in creationCard"
          :key="index"
          >
            <div class="landing_creations_img"><img :src="item.image1" alt=""></div>
            <p class="landing_creations_card_des">{{item.line1}}<br>{{item.line2}}</p>
          </li>
        </ul>
        <ul class="landing_creations_card_desktop">
          <li
          v-for="(item, index) in creationCard"
          :key="index"
          >
            <div class="landing_creations_img"><img :src="item.image2" alt=""></div>
            <p class="landing_creations_card_des">{{item.line1}}<br>{{item.line2}}</p>
          </li>
        </ul>
        <button class="landing_creations_all">SEE ALL</button>
      </section>
    </main>
    <footer>
      <div class="container">
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
          image1: require('./assets/images/mobile/image-deep-earth.jpg'),
          image2: require('./assets/images/desktop/image-deep-earth.jpg'),
          line1: 'DEEP',
          line2: 'EARTH'
        },
        {
          image1: require('./assets/images/mobile/image-night-arcade.jpg'),
          image2: require('./assets/images/desktop/image-night-arcade.jpg'),
          line1: 'NIGHT',
          line2: 'ARCADE'
        },
        {
          image1: require('./assets/images/mobile/image-soccer-team.jpg'),
          image2: require('./assets/images/desktop/image-soccer-team.jpg'),
          line1: 'SOCCER',
          line2: 'TEAM VR'
        },
        {
          image1: require('./assets/images/mobile/image-grid.jpg'),
          image2: require('./assets/images/desktop/image-grid.jpg'),
          line1: 'THE',
          line2: 'GRID'
        },
        {
          image1: require('./assets/images/mobile/image-from-above.jpg'),
          image2: require('./assets/images/desktop/image-from-above.jpg'),
          line1: 'FROM UP',
          line2: 'ABOVE VR'
        },
        {
          image1: require('./assets/images/mobile/image-pocket-borealis.jpg'),
          image2: require('./assets/images/desktop/image-pocket-borealis.jpg'),
          line1: 'POCKET',
          line2: 'BOREALIS'
        },
        {
          image1: require('./assets/images/mobile/image-curiosity.jpg'),
          image2: require('./assets/images/desktop/image-curiosity.jpg'),
          line1: 'THE',
          line2: 'CURIOSITY'
        },
        {
          image1: require('./assets/images/mobile/image-fisheye.jpg'),
          image2: require('./assets/images/desktop/image-fisheye.jpg'),
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
