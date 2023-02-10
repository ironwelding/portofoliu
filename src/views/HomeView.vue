<template>
  <div class="home">
    <div class="abstract-shape-shadow">
      <div class="abstract-shape"></div>
    </div>
    <nav>
      <section class="logo-container">
        <img alt="Vue logo" src="../assets/logo.png" id="logo">
        <h1>Iron welding</h1>
      </section>

      <div class="info">
        <section>
          <div class="info-group">
            <span class="material-icons">schedule</span>
            <p>L-V, 08:00 - 18:00</p>
          </div>
          <div class="info-group">
            <span class="material-icons">phone</span>
            <a href='tel:+40372659700'><p>0750 732 123</p></a>
          </div>
        </section>
        <section>
          <div class="info-group clickable" @click="seeLocationOnMap">
            <span class="material-icons">location_on</span>
            <p>Strada Gării 19, Cluj-Napoca, Romania</p>
          </div>
        </section>
      </div>

      <div class="language-holder">
        <span class="lang">EN</span>
        <div class="divider"></div>
        <span class="lang active">RO</span>
      </div>
    </nav>

    <div class="hero-section">
      <section>
        <h1 class="hero-title">IRON WELDING</h1>
        <h3 class="hero-subtitle"><span>pentru</span> noi metalul este doar o plastilină, îl modelăm cum vrem</h3>
      </section>
      <section class="gap-1">
        <p>Suntem <span>experți</span> în meșteșugul metalului</p>
        <p>Executăm confecții metalice și în străinătate</p>
      </section>
      <section>
        <p class="bold">Ne ocupăm cu:</p>
      </section>
      <section class="hero--wedo">
        <section>
          <p class="flx"><span class="circle"></span> automatizări porți:</p>
          <ul>
            <li>
              <span class="material-icons">trending_flat</span>
              batante
            </li>
            <li>
              <span class="material-icons">trending_flat</span>
              culisante
            </li>
            <li>
              <span class="material-icons">trending_flat</span>
              autoportante
            </li>
          </ul>
        </section>
        <section>
          <p class="flx"><span class="circle"></span> sudăm piese din:</p>
          <ul>
            <li>
              <span class="material-icons">trending_flat</span>
              inox
            </li>
            <li>
              <span class="material-icons">trending_flat</span>
              fier
            </li>
            <li>
              <span class="material-icons">trending_flat</span>
              aluminiu
            </li>
          </ul>
        </section>
      </section>
    </div>

    <div class="cards-container">
      <router-link v-for="card in categories" :key="card.clasa" :to="card.route">
        <div class="categ-card" :class="card.clasa" >
          <img :src="card.img">
          <div class="description">{{ card.text }}</div>
        </div>
      </router-link>
    </div>

    <div class="social-media-container">
      <a :href="cont.url" v-for="cont in contact" :key="cont.background" :target="cont.target">
        <div class="social-media" :style="{'background':cont.background}">
          <img :src="cont.icon">
        </div>
      </a>
    </div>
  </div>
</template>

<script setup>
import { ref } from '@vue/reactivity'

import facebookIcon from '@/assets/icons/icon-facebook.svg'
import callIcon from '@/assets/icons/icon-call.svg'
import locationIcon from '@/assets/icons/icon-location.svg'
import yahooIcon from '@/assets/icons/icon-yahoo.svg'
import photosIcon from '@/assets/icons/icon-photos.svg'

import terraceImg from '@/assets/img/terrace.jpg'
import stairsImg from '@/assets/img/stairs.jpg'
import ornamentalImg from '@/assets/img/ornamental.jpg'
import fencesImg from '@/assets/img/fences.jpg'

const locatieArmatura = 'https://www.google.com/maps/place/Arm%C4%83tura/@46.7870017,23.5818298,15z/data=!4m16!1m9!3m8!1s0x47490ea53279393b:0x42e40dbc022a794c!2sStrada+G%C4%83rii+19,+Cluj-Napoca+400394,+Romania!3b1!8m2!3d46.7870017!4d23.5905845!10e5!16s%2Fg%2F11c2fx2b4z!3m5!1s0x47490ea57bfc7bff:0xb7da6c68e1ec322b!8m2!3d46.7870017!4d23.5905845!16s%2Fg%2F1tffy8m_'

const contact = ref([
  {
    url: "https://www.facebook.com/profile.php?id=100063821432342",
    icon: facebookIcon,
    background: "#9BB9B9",
    target: '_blank'
  },
  {
    url: "mailto:ironwelding2020@yahoo.com",
    icon: yahooIcon,
    background: "#93B1B0",
    target: '_self'
  },
  {
    url: "tel:+40372659700",
    icon: callIcon,
    background: "#8FABAB",
    target: '_self'
  },
  {
    url: locatieArmatura,
    icon: locationIcon,
    background: "#88A3A5",
    target: '_blank'
  },
  {
    url: "https://photos.google.com/share/AF1QipMJELjODHUCFAjV_l1qde2wbWHTJp6WwnQODWo4uMuKnkC_1wxv8MxjNNkGWZH0hg?key=eDhWMHNJM0FfTmR0QW1RdnRhMWpQVVl1TzVtTlFR",
    icon: photosIcon,
    background: "#7A9395",
    target: '_blank'
  }
])

const categories = [
  {
    img: terraceImg,
    text: 'Terase & copertine',
    clasa: 'top-left',
    route: '/category/terraces'
  },
  {
    img: stairsImg,
    text: 'Balustrade & scări',
    clasa: 'top-right',
    route: '/category/stairs'
  },
  {
    img: fencesImg,
    text: 'Porți & garduri',
    clasa: 'bottom-left',
    route: '/category/fences'
  },
  {
    img: ornamentalImg,
    text: 'Confecții',
    clasa: 'bottom-right',
    route: '/category/confections'
  },
]

const seeLocationOnMap = () =>{ window.open(locatieArmatura, '_blanc') }


</script>