<template>
  <ExamplesUsageExample
    v-model="model"
    :code="code"
    :options="options"
    :name="name"
  >
    <div>
      <v-range-slider v-bind="props"></v-range-slider>
    </div>

    <template v-slot:configuration>
      <v-checkbox v-model="disabled" label="Disabled"></v-checkbox>
    </template>
  </ExamplesUsageExample>
</template>

<script setup>
  const name = 'v-range-slider'
  const model = ref('default')
  const options = ['vertical']
  const disabled = ref(false)
  const props = computed(() => {
    return {
      direction: model.value === 'vertical' ? 'vertical' : undefined,
      disabled: disabled.value || undefined,
    }
  })

  const slots = computed(() => {
    return ``
  })

  const code = computed(() => {
    return `<${name}${propsToString(props.value)}>${slots.value}</${name}>`
  })
</script>
