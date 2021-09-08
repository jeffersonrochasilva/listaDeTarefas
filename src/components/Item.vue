<template>
  <div id="item">
    <ul>
      <li v-for="list in lista" :key="list">
        <span>{{ list.text }}</span>
        <button @click="deleteitem(list.key)">concluir</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["lista", "deleter"],
  methods: {
    deleteitem(key) {
      deleter(key);
    },
  },
};
</script>
<style scoped>
#item {
  white-space: pre-wrap;
  word-wrap: break-word;
}

ul {
  list-style: none;
  padding: 0;
  margin-top: 20px;
}

ul li {
  padding: 15px 0;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}
li:not(:first-child) {
  border-top: 1px solid #eee;
}

span {
  color: #0d2636;
}

button {
  cursor: pointer;
  border-radius: 4px;
  padding: 8px;
  background: #ddd;
  border-style: none;
  border: 0;
  color: #000;
  outline: none;
}
</style>
