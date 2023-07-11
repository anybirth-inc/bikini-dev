<template>
  <div class="talk">
    <div class="chara">
      <!-- <img :src="require('../assets/charactor/smile.png')" /> -->
      <img :class="[{'charaImg': true},{'updown': isShow2}]" src="../assets/charactor/smile.png">
    </div>
    <p :class="[{'chat': true},{'isShow': isShow}]">
おはよ
    </p>
    <div class="input-chat">
      <input
      v-model="text"
      @input="event">
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
      emotion: 'smile',
      text: "",
      // chat: "chat",
      isShow: false,
      isShow2: false,
    }
  },
  methods: {
    event: function() {
      // alert(value);
      if (this.text == "おはよ") {
        this.isShow = true;
        this.isShow2 = true;
        setTimeout(() => {
          this.isShow2 = false;}
        ,3000
      )
        console.log(this.text);
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.talk {
  background-image: url("../assets/_living_3.jpg");
  background-repeat: no-repeat;
    background-size: cover;
    background-position-x: right;
  width: 100%;
  height: 100%;
  position: absolute;
  top:0;
  right:0;
  bottom:0;
  left:0;
  overflow: hidden;
}
.charaImg {
  position: absolute;
    right: 20px;
    bottom: 0;
    height: 66vh;
}
.chat {
  display: inline-block;
    position: absolute;
    bottom: -30px;
    right: 24px;
    padding: 5px 25px;
    background: #ffffff7a;
    border-radius: 8px;
    border: 1px solid #a5a5a5;
    transition: all 7s 1s ease-in-out;
    /* opacity: 0; */
}
.chat.isShow {
  /* opacity: 1; */
  bottom: 100%;
}
.input-chat {
  position: absolute;
    bottom: 12px;
    right: 0;
    left: 0;
    padding: 8px;
    margin: auto;
    width: 80%;
    height: 80px;
    background: #ffffff80;
    border-radius: 20px;
}
.input-chat input {

  width: 86%;
    border-radius: 12px;
    border: none;
    height: 22px;
    margin-top: 4px;

}

.updown {
    animation-name:updown1;   /* アニメーション名の指定 */
    animation-delay:0s;   /* アニメーションの開始時間指定 */
    animation-duration: 3s;   /* アニメーション動作時間の指定 */
    animation-timing-function: ease-in-out;  /* アニメーションの動き指定（徐々に早く）*/
    animation-iteration-count: infinite; 
}
@keyframes updown1 {
  0% {
    transform: translateY(0);
  }
  40% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
  65% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(0);
  }
}
</style>
