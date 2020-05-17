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
    title: 'Choisi ta fréquence',
    description: "On te suggère de recevoir ton élixir format 1L chaque mois pour combattre efficacement les RADs chaque jour. Mais tu peux choisir d'en recevoir qu'au 3 mois ou à toute les 2 semaines. Et tu peux en commander plus pour toute la famille !",
    color: 'orange'
  },
  {
    number: '2.',
    image: 'fas fa-truck',
    title: 'Livraison rapide',
    description: "Ton élixir est expédié 3-5 jours après que tu es placé ta commande et arrive frais chez toi. Ensuite on s'occupe de t'envoyer tes prochaines commandes à la fréquence que tu as choisis. Voilà !",
    color: 'white'
  },
  {
    number: '3.',
    image: 'far fa-clock',
    title: 'Dose quotidienne',
    description: "Pour des bienfaits optimals, nous recommandons 125 ml d'élixir chaque jour.",
    color: 'white'
  },
  {
    number: '4.',
    image: 'far fa-calendar-alt',
    title: 'Gère ton abonnement',
    description: "Que ce soit pour mettre en pause ton abonnement, canceler, gérer tes options de paiements. Tu n'as qu'à te connecter à ton compte.",
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
