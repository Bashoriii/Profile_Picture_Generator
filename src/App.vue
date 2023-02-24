<script>
export default {
  data() {
    return {
      picture: "",
      name: "",
    };
  },
  methods: {
    getPicture() {
      if (this.name) {
        this.picture = `https://robohash.org/${this.name}`;
      }
    },
  },
};
</script>

<template>
  <main>
    <div class="container">
      <input
        class="get-input"
        placeholder="Ketik nama Anda..."
        v-model="name"
      />
      <button class="btn-ava" @click="getPicture">Buat Avatar</button>
      <div v-if="picture" class="picture-container">
        <img class="avatar" v-bind:src="picture" />
      </div>
    </div>
  </main>
</template>

<style>
main {
  height: 90vh;
  width: 95vw;
  display: flex;
  justify-content: center;
  align-items: center;
}
.container {
  padding: 15px;
  border-radius: 5px;
  background-color: rgb(13, 170, 209);
  display: flex;
  flex-direction: column;
  gap: 15px;
}
.get-input {
  padding: 5px;
  border-radius: 5px;
  font-size: 15px;
  border: 1px #d4d4d4 solid;
}
.btn-ava {
  background-color: green;
  border: none;
  padding: 10px;
  color: white;
  border-radius: 8px;
  font-size: 16px;
}
.avatar {
  border-radius: 100%;
  background-color: #ffffff;
  border: 3px #c2c1c1 solid;
}
</style>
