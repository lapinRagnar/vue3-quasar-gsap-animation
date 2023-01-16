<template>
  <q-page padding>
    <q-btn
      color="orange"
      label="Mon super bouton"
      class="mon-super-bouton"
    ></q-btn>
    <q-btn
      color="green"
      label="Mon super bouton 2"
      class="mon-super-bouton2"
    ></q-btn>
  </q-page>
</template>

<script setup>
  import { gsap } from 'gsap'
  import { onMounted } from 'vue'

  onMounted(() => {
    console.log('salut')
    gsap.to(
      '.mon-super-bouton',
      {
        x: '50vh',
        y: '50vh',
        rotate: 360,
        ease: 'bounce',
        duration: 2
      }
    )

    gsap.from(
      '.mon-super-bouton2',
      {
        delay: 2,
        x: '50vh',
        y: '50vh',
        rotate: 360,
        ease: 'bounce',
        duration: 2
      }
    )
  })

</script>
