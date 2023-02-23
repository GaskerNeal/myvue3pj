<template>
   <h1>Hi{{title}}</h1>
   <div v-if="showModal">
    <NewModal :header = "header" :content="content" :theme = "theme" @close="showModal = false">
      <h1>Login Success!!</h1>
      <p>Welcome User MMS</p>
      <template v-slot:links>
        <a href="">Sign Up</a>
        <a href="">Register</a>
      </template>
    </NewModal>
   </div>
  <div v-if="shownextModal">
    <NextModal :header = "header" :content="content" :theme = "theme" @close="shownextModal = false">
      <h1>Login Failed!!</h1>
      <p>Welcome User MMS</p>
      <template v-slot:links>
        <a href="">Sign Up</a>
        <a href="">Register</a>
      </template>
    </NextModal>
   </div>
   <button @click="showModal=true">open modal</button>
   <button @click="shownextModal=true">open next modal</button>
</template>

<script>
import NewModal from "./components/NewModal.vue";
import NextModal from "./components/NextModal.vue";
export default {
  data() {
    return {
      title : " Myo Myint Soe",
      header : "Login Success!!",
      content : "Welcome User MMS",
      theme : "success",
      showModal : false,
      shownextModal : false
    }
  },
  components:{
      NewModal,
      NextModal
    }
}
</script>

<style scoped>
h1 {
  color : blue;
}
</style>
