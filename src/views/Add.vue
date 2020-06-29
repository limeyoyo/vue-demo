<template>
  <div>
    <p>标题</p>
    <input type="text" v-model="title" />
    <p>内容</p>
    <input type="text" v-model="content" />
    <div class="btn" @click="add()">添加</div>
  </div>
</template>

<script>
import store from "../store/index"
export default {
  name: "Add",
  store,
  data() {
    return {
      title: "",
      content: ""
    }
  },
  methods: {
    add() {
      store.commit("addItem", {
        title: this.title,
        content: this.content
      })
      this.title = ""
      this.content = ""
      this.$router.push("/home/list")
    }
  }
}
</script>

<style lang="stylus" scoped>
.btn {
  height: 20px;
  text-align: center;
  border-top: 1px solid #42b983;

  a {
    color: #42b983;
    display: block;
  }
}
</style>
