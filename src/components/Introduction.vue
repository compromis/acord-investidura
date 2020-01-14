<template>
  <div class="introduction">
    <div v-if="language == 'val'">
      <p>Avancem en el compliment dels <strong>compromisos adquirits davant la ciutadania</strong>,
        uns compromisos que complim gràcies a polítiques valentes amb les quals poder rescatar persones,
        recuperar la democràcia, canviar el model productiu, defensar el nostre territori
        i posar les institucions al servei de les persones.</p>

      <p>Ací pots conèixer en quin estat es troben cada un dels objectius marcats
        pel Consell en aquestos primers anys de govern, perquè en <strong>Compromís</strong> creiem
        que <strong>un govern honest i transparent</strong> és aquell que rendeix comptes davant de la ciutadania. </p>
    </div>
    <div v-else>
      <p>Avanzamos en el cumplimiento de los <strong>compromisos adquiridos ante la ciudadanía</strong>,
        unos compromisos que cumplimos gracias a políticas valientes con las que poder
        rescatar personas, recuperar la democracia, cambiar el modelo productivo, defender
        nuestro territorio y poner las instituciones al servicio de las personas.</p>

      <p>Aquí puedes conocer en qué estado se encuentran cada uno de los objetivos
        marcados por el Consell en estos primeros años de gobierno, porque en <strong>Compromís</strong>
        creemos que <strong>un gobierno honesto y transparente</strong> es aquel que rinde cuentas ante la ciudadanía. </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'introduction',

  props: {
    language: {
      type: String,
      default: 'val'
    }
  }
}
</script>

<style lang="scss" scoped>
  p {
    font-size: 1.75rem;
    text-align: justify;
    margin-bottom: 2rem;
  }
</style>
