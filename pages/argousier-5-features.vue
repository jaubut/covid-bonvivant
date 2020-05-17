<template>
  <div class="flex-container">
    <div v-for="item in feature" :key="item.id" class="group-container">
      <div class="img-container">
        <i :class="item.img" />
      </div>
      <div class="text-container">
        <h3>{{ item.title }}</h3>
        <p>{{ item.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
const data = [
  {
    img: 'fas fa-blender',
    title: 'Pressé à froid',
    description: "Notre élixir d'argousier est pressé à froid pour garder son intégrité et sa puissante efficacité."
  },
  {
    img: 'fas fa-tree',
    title: 'De la ferme',
    description: "Notre plantation d'argousier est soigneusement entretenue pour vous offrir le meilleur produit, de la ferme à votre table."
  },
  {
    img: 'far fa-smile-beam',
    title: 'Goût puissant',
    description: "À chaque dose vous recentez toute la puissance contenue dans l'argousier."
  },
  {
    img: 'fas fa-hand-holding',
    title: 'Cueillit à la main',
    description: 'Chaque récolte est soigneusement opérer par notre équipe, à la main.'
  },
  {
    img: 'far fa-thumbs-up',
    title: "Rien d'autres",
    description: "Aucun ajout, ni agent de conservation. Le fruit de l'argousier, rien d'autres."
  }
]
export default {
  data () {
    return {
      feature: data
    }
  }
}
</script>

<style scoped>
.flex-container {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-content: space-around;
  background: #F4FBF2;
}
.group-container {
  display: flex;
  flex-flow: row nowrap;
  width: 45vw;
  padding: 25px 35px;
}
.img-container {
  display: flex;
  justify-content: center;
  align-items: center;
  padding-right: 35px;
  font-size: 2.5rem;
}
.flex-container h3 {
  font-size: 2rem;
  font-weight: 800;
}
.flex-container p {
  font-size: 0.85rem;
  margin: 0;
}
.text-container {
  display: flex;
  flex-flow: column nowrap;
  text-align: left;
  align-items: flex-start;
  justify-content: center;
  padding-right: 10vw;
}
@media only screen and (max-width: 812px) {
  .flex-container h3 {
    font-size: 1.5rem;
  }
  .flex-container p {
    font-size: 0.5rem;
  }
  .img-container {
    font-size: 1.5rem;
  }
  .group-container {
    width: 90vw;
  }
  .text-container {
    padding-right: 2vw;
  }
}

</style>
