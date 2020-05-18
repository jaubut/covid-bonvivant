<template>
  <div class="flex-container">
    <div v-for="step in steps" :key="step.id" :class="'grid-container ' + step.color">
      <div class="number-container">
        <p>{{ step.number }}</p>
      </div>
      <div class="group-container">
        <div class="img-container">
          <i :class="step.image" />
        </div>
        <h3>{{ step.title }}</h3>
        <p>{{ step.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
const data = [
  {
    number: '1.',
    image: 'fas fa-glass-whiskey',
    title: 'Choisir sa fréquence',
    description: 'Le format 1L est suggéré pour avoir votre dose quotidienne, pendant tout le mois! Vous pouvez faire un achat unique ou profiter d’un abonnement mensuel, qui peut être cancellé à tout moment, sans tracas :)',
    color: 'orange'
  },
  {
    number: '2.',
    image: 'fas fa-truck',
    title: 'Livraison rapide',
    description: 'L’élixir est livré dans un délais d’environ 5 jours après que la commande soit passée, puis de façon automatique pour les prochains mois!',
    color: 'white'
  },
  {
    number: '3.',
    image: 'far fa-clock',
    title: 'Dose quotidienne',
    description: "Pour des bienfaits optimals, nous recommandons 125 ml d'élixir, chaque jour.",
    color: 'white'
  },
  {
    number: '4.',
    image: 'far fa-calendar-alt',
    title: 'Gère ton abonnement',
    description: "Si tu as besoin de mettre en pause ton abonnement, canceler, gérer tes options de paiements, tu n'as qu'à te connecter à ton compte.",
    color: 'orange'
  }
]
export default {
  data () {
    return {
      steps: data
    }
  }

}
</script>

<style scoped>
.flex-container {
  display: flex;
  flex-flow: row wrap;
  background: #F4FBF2;
}
.grid-container {
  width: 50%;
  display: grid;
  grid-template: repeat(2, 1fr) / repeat(2, 1fr);
}
.number-container {
  grid-area: 1/1/2/2;
  padding: 15px;
  font-size: 1.5rem;
}
.img-container {
  font-size: 3.5rem;
}
.group-container {
  grid-area: 1/1/3/3;
  display: flex;
  flex-flow: column;
  justify-content: flex-start;
  align-items: center;
  text-align: center;
  padding: 5rem;
}
.orange {
  background: orange;
}
</style>
