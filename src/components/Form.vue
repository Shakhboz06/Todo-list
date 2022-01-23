<template>
  <div id="addForm">
    <h1>To do List</h1>
    <form @submit="prevent()">
      <input type="text" v-model="show_Value" />
      <button @click="React" class="submit">Add</button>
    </form>
    <div class="line"></div>
  </div>
</template>

<script>
export default {
  name: "Form",
  data() {
    return {
      show_Value: "",
    };
  },
  methods: {
    React: function () {
      this.$emit("Send", this.show_Value);
    },
    prevent: function () {
      event.preventDefault();
      this.show_Value = "";
    },
  },
};
</script>

<style>
#addForm {
  font-family: "Gilroy";
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 20px 30px;
}
h1 {
  font-weight: 700;
  font-size: 48px;
}
form:focus-within {
  transition: 0.5s ease;
  box-shadow: 0px 0.2em 2.5em #f0f0f0;
  transform: scale(1.025);
}
form {
  margin-top: 20px;
  display: flex;
  grid-gap: 20px;
  background-color: #fffdfd;
}
form input {
  height: 35px;
  width: 321px;
  border-radius: 10px;
  border: 2px solid #007fff;
  box-sizing: border-box;
  padding: 5px;
  padding-left: 15px;
  font-weight: 600;
  font-size: 16px;
}
input:focus {
  outline-offset: 0.7px;
  outline: 1px solid #007fff;
  border: 1px solid #007fff !important;
}
.submit {
  font-family: "Gilroy";
  height: 35px;
  width: 155px;
  border-radius: 10px;
  background: #0071e3;
  border: #0071e3;
  color: #fff;
  font-size: 18px;
  font-style: normal;
  font-weight: 500;
  transition: 0.3s ease;
  cursor: pointer;
}
.submit:hover {
  transform: scale(1.025);
}
.line {
  margin: 30px;
  border: 1px solid #00000040;
  width: 80%;
  height: 0px;
}
</style>