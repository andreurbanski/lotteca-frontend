<template>
  <v-layout class="rounded rounded-md">
    <v-app-bar class="float-left">
      <v-img height="300" src="@/assets/logo.png" />
    </v-app-bar>

    <v-navigation-drawer>
      <Operations></Operations>
    </v-navigation-drawer>

    <v-main class="d-flex align-center justify-center" style="min-height: 300px;">
      <OperationDetail></OperationDetail>
    </v-main>
  </v-layout>
</template>


<script lang="ts" setup>
  import Operations from '@/components/Operations.vue'
  import OperationDetail from '@/components/OperationDetail.vue'
</script>
