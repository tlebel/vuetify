<template>
  <ExamplesUsageExample
    v-model="model"
    :code="code"
    :options="options"
    :name="name"
  >
    <div>
      <v-autocomplete v-bind="props"></v-autocomplete>
    </div>

    <template v-slot:configuration>
      <v-checkbox v-model="clear" label="Clearable"></v-checkbox>

      <v-checkbox v-model="chips" label="Chips"></v-checkbox>

      <v-checkbox v-model="multiple" label="Multiple"></v-checkbox>
    </template>
  </ExamplesUsageExample>
</template>

<script setup>
  const name = 'v-autocomplete'
  const model = ref('default')
  const clear = ref(false)
  const chips = ref(false)
  const multiple = ref(false)
  const options = ['outlined', 'underlined', 'solo', 'solo-filled', 'solo-inverted']
  const props = computed(() => {
    return {
      clearable: clear.value || undefined,
      chips: chips.value || undefined,
      label: 'Autocomplete',
      items: ['California', 'Colorado', 'Florida', 'Georgia', 'Texas', 'Wyoming'],
      multiple: multiple.value || undefined,
      variant: model.value === 'default' ? undefined : model.value,
    }
  })

  const slots = computed(() => {
    return ``
  })

  const code = computed(() => {
    return `<${name}${propsToString(props.value)}>${slots.value}</${name}>`
  })
</script>
