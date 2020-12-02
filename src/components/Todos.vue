<template>
  <div>
    <section class="text-gray-700 body-font">
      <div class="container px-5 py-5 mx-auto">
        <div class="flex flex-wrap lg:w-4/5 sm:mx-auto sm:mb-2 -mx-2">
          <div
            class="p-2 sm:w-1/1 w-full"
            v-bind:key="todo.id"
            v-for="todo in todos"
          >
            <div class="bg-gray-200 rounded flex p-4 h-full items-center">
              <svg
                fill="none"
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="3"
                class="text-indigo-500 w-6 h-6 flex-shrink-0 mr-4"
                viewBox="0 0 24 24"
              >
                <path d="M22 11.08V12a10 10 0 11-5.93-9.14"></path>
                <path d="M22 4L12 14.01l-3-3"></path>
              </svg>
              <span class="title-font font-medium">
                <TodoItem
                  v-bind:todo="todo"
                  v-on:del-todo="$emit('del-todo', todo.id)"
                />
              </span>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  name: "Todos",
  components: {
    TodoItem,
  },
  props: ["todos"],
};
</script>
