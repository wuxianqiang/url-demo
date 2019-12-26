<template>
  <div class="hello">
    <div>
      <textarea
        cols="30"
        rows="5"
        v-model="msg"
        class="link"></textarea>
      <button
        @click="handlerJSON"
        class="button">
        JSON格式化
      </button>
      <button
        @click="handlerUrl"
        class="button">
        URL格式化
      </button>
    </div>
    <div>
      <pre><code class="lang-json" ref="code">{{view}}</code></pre>
    </div>
  </div>
</template>

<script>
import Url from 'url-parse'

export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "",
      view: ""
    };
  },
  methods: {
    handlerJSON () {
      try {
        this.view = JSON.stringify(JSON.parse(this.msg), null, 2).trim();
      } catch (error) {
        alert('您输入的信息有误，请重新输入')
      }
    },
    handlerUrl() {
      try {
        this.view = JSON.stringify(new Url(this.msg, true), null, 2).trim();
      } catch (error) {
        alert('您输入的信息有误，请重新输入')
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  width: 100%;
  text-align: left;
}
.link {
  width: 100%;
  word-break: break-all;
}
</style>
