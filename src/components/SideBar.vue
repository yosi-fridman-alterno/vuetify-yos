<script lang="ts" setup>
import { defineEmits as dEmits }  from 'vue'  ;

const emits = dEmits(['selectOption']);

const selectOption = (isColor: boolean) => {
  emits("selectOption", isColor);
}
</script>

<template>
  <VNavigationDrawer expand-on-hover rail>

    <VList>
      <VListItem prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg" title="Yosi Fridman"
        subtitle="myyosi@gmailcom">
      </VListItem>
    </VList>

    <VDivider />

    <VList density="compact" nav>
      <VListItem prepend-icon="mdi-image" title="Color Gallery" value="color" @click="selectOption(true)"></VListItem>
      <VListItem prepend-icon="mdi-dialpad" title="Grayspace Gallery" value="color" @click="selectOption(false)">
      </VListItem>
    </VList>

  </VNavigationDrawer>
</template>
