<template>
    <q-tree
    :nodes="simple"
    node-key="label"
    />
</template>

<script>

export default {
  setup () {
    return {
      simple: [
        {
          label: 'abcde'
        }
      ]
    }
  }
}
</script>
