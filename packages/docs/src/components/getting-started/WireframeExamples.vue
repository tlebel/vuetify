<template>
  <v-row>
    <v-col
      v-for="([name, wireframe], i) in wireframes"
      :key="i"
      cols="12"
      md="6"
      lg="4"
    >
      <router-link
        :to="rpath(`/wireframes/${wireframe}/`)"
        class="text-decoration-none"
        rel="nofollow noopener"
        target="_blank"
      >
        <AppFigure
          :alt="`${name} layout`"
          :aspect-ratio="16/9"
          :title="name"
          :src="`https://cdn.vuetifyjs.com/docs/images/wireframes/${wireframe}.svg`"
          class="border"
        />
      </router-link>
    </v-col>
  </v-row>
</template>

<script setup>
  const wireframes = [
    'Baseline',
    'Extended toolbar',
    'System bar',
    'Inbox',
    'Constrained',
    'Side navigation',
    'Three column',
    'Discord',
    'Steam',
  ].map(wireframe => ([wireframe, kebabCase(wireframe)]))
</script>
