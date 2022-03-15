<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="vol-12">
          <h1 class="display-1 my-5">Crear Una Nueva lista de Tarea</h1>

          <div class="d-flex">
            <label for="nombre">Tarea</label>
            <input
              type="text"
              placeholder="nueva tarea"
              class="form-control"
              v-model="agregarTarea"
              @keyup.enter="agregoNew"
            />
            <button
              v-
              class="mx-1 btn btn-outline-secondary"
              type="button"
              v-on:click="agregoTarea"
            >
              Crear
            </button>
          </div>
          <div class="col-12">
            <h2 class="my-2">Lista</h2>
            <ul>
              <li
                class="list-group-item my-2"
                v-for="(tarea1, i) in tareaFinal"
                :key="i"
              >
                {{ tarea1 }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      tareaFinal: [],
      agregarTarea: "",
    };
  },
  methods: {
    agregoTarea() {
      this.agregarTarea === ""
        ? alert("crear tarea")
        : this.tareaFinal.push(this.agregarTarea);
      this.agregarTarea = "";
    },
  },
};
// data() {
//   return {
//     show: true,
//   };
// },
//};
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
