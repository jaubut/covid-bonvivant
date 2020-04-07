/* eslint-disable nuxt/no-globals-in-created */
<template>
  <div class="container-corona">
    <vue-typed-js
      :strings="items"
      :loop="true"
      :type-speed="200"
      :back-speed="100"
    >
      <h1>
        Thanks <span class="typing" /> <br> d'avoir contribué à aider <transition name="slide" mode="out-in">
          <span v-if="currentNum % 2 === 0" key="x">{{ currentNum }}</span> <span v-else key="y">{{ currentNum }}</span>
        </transition> héros de la santé.
      </h1>
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
          })
        }
      })
  },
  data () {
    return {
      items: [],
      number: 5,
      currentNum: 0,
      interval: null
    }
  },
  mounted () {
    this.interval = setInterval(() => {
      if (this.number > this.currentNum) {
        this.currentNum++
      } else {
        return this.currentNum === 0
      }
    }, 1000)
  }
}
</script>

<style>
.container-corona {
  display: flex;
  flex-flow: column wrap;
  height: 100vh;
  width: 100vw;
  background: #F4FBF2;
  justify-content: center;
  align-content: center;
  text-align: center;
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
