<template>
  <div id="app">
    <h2>Rannie Yang 的在线小翻译</h2>
    <h5>方便 / 快捷 / 准确</h5>
    <Form @formSubmit="translate"></Form>
    <Translate :translateAnswer="answer"></Translate>
  </div>
</template>

<script>
import Form from './components/Form'
import Translate from './components/Translate'

export default {
  name: 'App',
  components: {
    Form,
    Translate
  },
  data(){
    return {
      name:'love yrl!!!!!',
      answer:'',
    }
  },
  methods:{
    translate:function(text,mode) {
      this.answer = '请稍等...... 接口在国外有点慢'
      this.$http.get("https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180705T095213Z.00c9da3e3fbd0223.72db6691e61604ad179e50157ba565f7943ef103&lang="+ mode +"&text="+text)
      .then((a) => {
        console.log(a.body.text[0]);
        this.answer = a.body.text[0];
      })
      
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
