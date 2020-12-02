<template>
  <div>
    <div class="text-center mb-5">
      <h1
        class="sm:text-3xl text-2xl font-medium text-center title-font text-gray-900 mb-4"
      >
        Todo List Using Vuejs and Tailwind
      </h1>
    </div>
    <section class="text-gray-700 body-font">
      <div class="container px-5 py-1 mx-auto">
        <div class="flex flex-wrap lg:w-4/5 sm:mx-auto sm:mb-2 -mx-2">
          <div class="p-2 w-full">
            <form @submit.prevent="addTodo">
              <input
                type="text"
                v-model="title"
                name="title"
                class="sm:w-5/6 bg-gray-100 rounded border border-gray-300 focus:border-indigo-500 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out"
                placeholder="Add Todo..."
              />

              <input
                type="submit"
                value="Submit"
                class="sm:w-5/1 text-white bg-indigo-500 border-0 ml-5 py-2 px-8 focus:outline-none hover:bg-indigo-600 rounded text-lg"
              />
            </form>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
// import uuid from 'uuid';
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo() {
      const newTodo = {
        title: this.title,
        completed: false,
      };
      // Send up to parent
      this.$emit("add-todo", newTodo);

      this.title = "";
    },
  },
};
</script>
