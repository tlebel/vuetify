<template>
  <ApiApiTable :headers="headers">
    <template #row="{ props, item }">
      <tr v-bind="props">
        <ApiNameCell section="props" :name="kebabCase(item.name)" :new-in="item.newIn" />

        <td>
          <ApiPrismCell :code="item.formatted" />
        </td>

        <td>
          <ApiPrismCell :code="item.default" />
        </td>
      </tr>
    </template>
  </ApiApiTable>
</template>

<script setup lang="ts">
  const headers = ['name', 'type', 'default']
</script>
