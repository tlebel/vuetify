<template>
  <a
    :href="product.href"
    class="text-high-emphasis text-decoration-none"
    rel="noopener"
    target="_blank"
  >
    <AppFigure
      :alt="product.title"
      :name="product.title"
      :src="product.src"
      cover
      height="230"
      max-height="230"
      min-height="230"
    >
      <figcaption class="d-flex text-subtitle-2 align-center text-capitalize mt-3">
        <span v-text="product.title" />

        <v-chip
          v-if="product.price === 0"
          class="text-uppercase px-1 ms-2"
          color="primary"
          label
          size="x-small"
          text="Free"
        />

        <span
          v-else
          class="ms-auto text-subtitle-1 font-weight-bold"
          v-text="`$${product.price}`"
        />
      </figcaption>
    </AppFigure>
  </a>
</template>

<script setup>
  defineProps({
    product: {
      type: Object,
      default: () => ({}),
    },
  })
</script>
