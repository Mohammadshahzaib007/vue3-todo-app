<script setup>
defineProps(["name"]);
const emits = defineEmits(["update:name"]);

const onChange = (event) => {
  emits("update:name", event.target.value);
};
</script>

<template>
  <section class="greeting">
    <h2 class="title">
      What's up,
      <input
        type="text"
        placeholder="Name here"
        :value="name"
        @input="onChange"
      />
    </h2>
  </section>
</template>
