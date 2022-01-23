<template>
  <div id="app">
    <Form @Send="load" />
    <main>
      <div class="wrapper">
        <Todo
          v-for="item of todos"
          :key="item.id"
          :operate="item"
          @deleted="reload"
        />
      </div>
    </main>
  </div>
</template>

<script>
import Form from "./components/Form.vue";
import Todo from "./components/Todo.vue";
export default {
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    load: function (text) {
      if (text.length < 3) {
        alert("Please enter a task!");
      } else {
        this.todos.push({
          id: Math.random().toString().slice(2, 4),
          task: text,
          time: new Date().getHours() + ":" + new Date().getMinutes(),
          isDeleted: false,
          del_icon: "/icons/2561211_circle_x_icon.svg",
        });
        console.log(this.todos);
      }
    },
    reload: function (operate) {
      this.todos = this.todos.filter((item) => item !== operate);
    },
  },
  components: {
    Form,
    Todo,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  max-width: 1440px;
  margin: 0 auto;
}
</style>