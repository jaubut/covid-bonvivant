<template>
  <div class="flex-container">
    <div>
      <h3>3x <i class="fas fa-atom" /></h3>
      <p>3x plus d’antioxydants que la canneberge. L’argousier est le petit fruit qui en contient le plus.</p>
    </div>
    <div>
      <h3>103%</h3>
      <p>103% de la valeur journalière recommandé en Vitamine C, dans chaque dose de 30 ml.</p>
    </div>
    <div>
      <h3>Ω-7</h3>
      <p>Les Oméga-7 contribuent à l'hydratation de la peau, le bon fonctionnement du foi en plus d'avoir une action anti-inflammatoire.</p>
    </div>
    <div>
      <h3>Stérol</h3>
      <p>Les stérols végétaux permettent de réduire le taux de mauvais cholésterol (LDL) sanguin.</p>
    </div>
  </div>
</template>

<script>
export default {

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
.flex-container div {
  display: flex;
  flex-flow: column nowrap;
  width: 20vw;
  justify-content: flex-start;
  align-items: center;
  text-align: center;
  padding: 15px;
}
.flex-container h3 {
  font-size: 3.5rem;
  font-weight: 800;
}
.flex-container p {
  font-size: 0.85rem;
}
@media only screen and (max-width: 812px) {
  .flex-container div {
    width: 45vw;
  }

}

</style>
