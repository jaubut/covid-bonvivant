/* eslint-disable nuxt/no-globals-in-created */
<template>
  <div class="container-corona">
    <!-- <img class="image-corona" src="@/assets/covid-19-image-boite-personne.svg" alt=""> -->
    <vue-typed-js
      :strings="items"
      :loop="true"
      :type-speed="200"
      :back-speed="100"
    >
      <h3 style="margin:auto;">
        Merci <span class="typing" /> <br> d'avoir contribué à aider <transition name="slide" mode="out-in">
          <span v-if="currentNum % 2 === 0" key="x">{{ currentNum }}</span> <span v-else key="y">{{ currentNum }}</span>
        </transition> héros de la santé.
      </h3>
    </vue-typed-js>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Index',
  components: {
  },
  asyncData ({ params }) {
    return axios.get('https://api.airtable.com/v0/' + 'app0yxn9b11rdmbd8' + '/covid-19', {
      headers: {
        Authorization: 'Bearer ' + 'keyYpAgTFas9oMW80'
      }
    })
      .then((res) => {
        return {
          items: res.data.records.map((i) => {
            i.people = i.fields.Name
            return i.people
          }),
          numbers: res.data.records.map((n) => {
            n.barre = n.fields.barres
            return n.barre
          })
        }
      })
  },
  data () {
    return {
      currentNum: 0,
      interval: null
    }
  },
  mounted () {
    this.interval = setInterval(() => {
      if (this.numbers.reduce((a, b) => a + b, 0) > this.currentNum) {
        this.currentNum++
      } else {
        return this.currentNum === 0
      }
    }, 300)
  }
}
</script>

<style>
html {
  background: #F4FBF2;
}
.container-corona {
  display: flex;
  flex-flow: column wrap;
  height: 100%;
  width: 100vw;
  background: #F4FBF2;
  justify-content: flex-start;
  align-content: center;
  text-align: center;
}
.image-corona {
  width: 50%;
  align-self: center;
  margin-bottom: 4rem;
}
.slide-enter {
  top: 10px;
  opacity: 0.5;
}

.slide-enter-active, .slide-leave-active {
  transition: all .15s;
}

.slide-enter-to {
  top: 0px;
  opacity: 1;
}

.slide-leave {
  top: 0px;
  opacity: 1;
}

.slide-leave-to {
  top: -30px;
  opacity: 0;
  transform: blur(8px);
}
</style>
