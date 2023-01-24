<template>
  <div id="app">
    <!-- form を submit すると sendMessage が呼ばれます -->
    <form @submit.prevent="sendMessage">
      <!-- 名前とメッセージの各 input タグの入力値は、 それぞれ inputName, inputMessage と同期されます -->
      <input type="text" v-model="inputName" placeholder="名前" /><br />
      <input type="text" v-model="inputMessage" placeholder="メッセージ" /><br />
      <button type="submit">送信</button>
    </form>
    <ul>
      <!-- messages に入っているメッセージをループして出力します -->
      <li v-for="message in messages" :key="message.id">
        <!-- message はオブジェクトで、 name, message, id, ここにはないですが createdAt 属性があることを期待しています -->
        <b>{{ message.name }}</b> {{ message.message }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      messages: [],
      inputName: "",
      inputMessage: "",
    };
  },
  methods: {
    sendMessage() {
      // TODO: メッセージを送信
    },
    getMessages() {
      // TODO: メッセージを取得
    },
    subscribeMessage() {
      // TODO: メッセージを購読
    },
    unsubscribeMessage() {
      // TODO: メッセージを購読をやめる
    },
  },
  mounted() {
    this.getMessages()
    this.subscribeMessage()
  },
  beforeDestroy() {
    this.unsubscribeMessage()
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
