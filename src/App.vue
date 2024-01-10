<script setup lang="ts">
import Button from './components/Button.vue' 
import CardLaser from './components/CardLaser.vue' 
</script>

<template>
  <div id="dwn-wrapper">
    <div class="container">
      <CardLaser />
    </div>
  </div>
  <Button @on-click="capture" />
</template>

<script lang="ts">
import html2canvas from "html2canvas";

export default {
  methods: {
    capture() {
      const element = document.getElementById('dwn-wrapper')!;
      html2canvas(element, {
        useCORS: true,
        allowTaint: true,
        foreignObjectRendering: false,
        logging: true,
      }).then((canvas) => {
        const image = canvas.toDataURL('image/png');
        const link = document.createElement('a');
        link.href = image;
        link.download = `${new Date().getTime()}.png`;
        link.click();
      });
    }
  }
}
</script>

<style scoped></style>
