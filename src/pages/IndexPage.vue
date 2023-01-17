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

    <div id="quote">SplitText makes it easy to break apart the text in an HTML element so that each character, word, and/or line is wrapped in its own div tag.</div>

  </q-page>
  
</template>

<script setup>
  import { gsap } from 'gsap'
  import { onMounted } from 'vue'


  onMounted(() => {
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

    gsap.from(
      '.mon-super-bouton',
      {
        delay: 4,
        x: '50vh',
        y: '50vh',
        rotate: 360,
        ease: 'bounce',
        duration: 4
      }
    )


  })

</script>
