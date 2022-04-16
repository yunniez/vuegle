<template>
  <div class="main">
    <div class="logo">
      <span>V</span><span>u</span><span>e</span><span>g</span><span>l</span><span>e</span>
    </div>
    <input type="search" :value="item" @keyup.enter="search(item)" @change="changeName($event)">
    <div class="buttons">
      <button class="bookmark" v-for="item in items" :key="item" v-on:click="search(item)">{{ item }}</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      안녕: "안녕하세요",
      isMonday: true,
      items: ["천우희", "신하균", "송혜교"],
    };
  },
  methods: {
    hello: function () {
      alert("hello");
    },
    search: function (item) {
      alert(item+" 검색 시작합니다.");
      var url = "https://www.google.com/search?q="+item+"&rlz=1C1CAFC_enKR874KR874&oq="+item+"&aqs=chrome..69i57j46i433i512j0i512l8.2156j0j15&sourceid=chrome&ie=UTF-8";
      window.open(url, "_blank");
    },
    changeName($event){
      this.item = $event.target.value;
    }
  },
};
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

.main{
  align-items: center;
  display: flex;
  flex-direction: column;
  height: 6 00px;
  min-width: fit-content;
  padding-top: 100px;
  position: relative;
  z-index: 1;
}

.logo {
  font-weight: 600;
  font-size: 50pt;
  margin:30px;
}

.logo span:nth-child(1) {
        color:#4285f4;
}
.logo span:nth-child(2) {
    color:#ea4335;
}
.logo span:nth-child(3) {
    color:#fbbc05;
}
.logo span:nth-child(4) {
    color:#4285f4;
}
.logo span:nth-child(5) {
    color:#34a853;
}
.logo span:nth-child(6) {
    color:#ea4335;
}

input{
  position: relative;
  width: 500px;
  height: 50px;
  margin:20px;
      padding-inline-end: 44px;
    padding-inline-start: 52px;
}

.bookmark{
  width:100px;
  height:100px;
  border: none;
  background: white;
  font-size: 20px;
  font-weight: 600;
}
</style>
