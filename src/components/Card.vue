<template>
  <div id="card">
    <form @submit.prevent="adicionar">
      <input v-model="tarefa" type="text" placeholder="Tarefas de hoje" />
      <button type="submit">Adcionar</button>
    </form>
    <Item :lista="tarefas" :deleter="deletecard" />
    <span v-show="tarefas.length > 0"
      >Você tem
      <strong class="pend: pendente">{{ tarefas.length }}</strong> tarefas
      pendentes</span
    >
  </div>
</template>

<script>
import Item from "./Item";
export default {
  // name: "#card",
  components: {
    Item,
  },
  data() {
    return {
      tarefa: "",
      pendente: false,
      tarefas: [],
    };
  },
  methods: {
    adicionar() {
      if (this.tarefa == "") {
        alert("Preencha o campo!");
      } else {
        this.tarefas.push({
          text: this.tarefa,
          key: Date.now(),
        });
        this.tarefa = "";
      }
    },
    deletecard(key) {
      // console.log("deletou" + key);
      let filtro = this.tarefas.filter((item) => {
        return item.key != key;
      });
      return (this.tarefas = filtro);
    },
  },
};
</script>

<style scoped>
#card {
  max-width: 700px;
  padding: 20px;
  background: #fff;
  border-radius: 4px;
  margin: 20px auto;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
}
.pendente {
  color: red;
}

form {
  margin-top: 30px;
  display: flex;
  flex-direction: row;
}

form button {
  cursor: pointer;
  background: #0f5959;
  border: 0;
  border-style: none;
  border-radius: 4px;
  margin-left: 10px;
  padding: 0 15px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
}
input {
  flex: 1;
  border-radius: 4px;
  padding: 6px 10px;
  border: 1px solid #eee;
  font-size: 14px;
  outline: none;
}
</style>
