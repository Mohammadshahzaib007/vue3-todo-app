<script setup>
defineProps(["inputCategory", "inputContent"]);
defineEmits(["update:inputCategory", "update:inputContent", "addTodo"]);
</script>

<template>
  <section class="create-todo">
    <h3>CREATE A TODO</h3>

    <form @submit.prevent="$emit('addTodo')">
      <h4>What's on your todo list?</h4>

      <input
        type="text"
        placeholder="e.g. Learn vue3"
        :value="inputContent"
        @input="$emit('update:inputContent', $event.target.value)"
      />

      <h4>Pick a category</h4>

      <div class="options">
        <label>
          <input
            type="radio"
            name="category"
            value="business"
            @input="$emit('update:inputCategory', $event.target.value)"
          />
          <span class="bubble business"></span>
          <div>Business</div>
        </label>

        <label>
          <input
            type="radio"
            name="category"
            value="personal"
            @input="$emit('update:inputCategory', $event.target.value)"
          />
          <span class="bubble personal"></span>
          <div>Persnoal</div>
        </label>
      </div>

      <input type="submit" value="Add todo" />
    </form>
  </section>
</template>
