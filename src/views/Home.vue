<template>
  <VApp>
    {{ isWithColor }}
    <!-- SIDEBAR -->
    <SideBar @selectOption="onSelectOption" />
    <VMain>
      <!-- CARDS -->
      <ImageGallery :isWithColor="isWithColor"/>
    </VMain>


  </VApp>
</template>

<script lang="ts" setup>
import SideBar from '@/components/SideBar.vue'
import ImageGallery from '@/components/ImageGallery.vue';
import { ref } from 'vue';

const isWithColor = ref(true);

const onSelectOption = (isColor: boolean) => {

  isWithColor.value = isColor;

}

</script>
