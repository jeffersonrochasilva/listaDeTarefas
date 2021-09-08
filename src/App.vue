<template>
  <div id="app">
    <header>
      Minhas tarefas
    </header>
    <Card />
  </div>
</template>
<script>
import Card from "@/components/Card";
export default {
  // name: "#app",
  components: {
    Card,
  },
  data() {
    return {
      nome: "jefferson",
    };
  },
};
</script>

<style lang="scss" scoped>
header {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 80px;
  font-size: 40px;
  color: #fff;
}
</style>
