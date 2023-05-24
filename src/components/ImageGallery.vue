<script setup lang="ts">
// import { defineProps as dProps } from 'vue';

const p = defineProps(["isWithColor"]);
const copyUrl = async (url: string) => {
  await navigator.clipboard.writeText(url);
  window.open(url, "__blank");
}
</script>

<template>
  <VCard class="mx-5 my-2 pa-3">
    <VRow>
      <VCol cols="4" sm="3" md="2" lg="1" v-for="n in 200" v-bind:key="n">
        <VHover v-slot="{ isHovering, props }">
          <VCard :elevation="isHovering ? 12 : 2" v-bind="props"
            @click="copyUrl(`https://picsum.photos/500/300?image=${n * 5 + 10}${p.isWithColor ? '' : '&grayscale'}`)">
            <VImg :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${p.isWithColor ? '' : '&grayscale'}`"
              :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${p.isWithColor ? '' : '&grayscale'}`"
              aspect-ratio="1" cover>
              <template v-slot:placeholder>
                <VRow class="fill-height ma-0" align="center" justify="center">
                  <VProgressCircular indeterminate color="grey-lighten-5" />
                </VRow>
              </template>
            </VImg>
          </VCard>
        </VHover>
      </VCol>
    </VRow>
  </VCard>
</template>
