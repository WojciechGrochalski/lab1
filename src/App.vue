<script>
import {defineComponent} from "vue";

export default defineComponent({

  data() {
    return {
      films: ['Głupi i głupszy'],
      film: ''
    };
  },
  methods: {
    remove(index) {
      this.films.splice(index, 1);

    },
    add() {
      this.films.push(this.film);
      this.film = ''
    }
  }
});
</script>


<template>
  <head>
    <!-- Inne tagi head -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
          integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">

  </head>
  <body>
  <table class="table table-striped table-hover">
    <thead>
    <tr>
      <th colspan="2"> Lista filmów</th>
      <th></th>
    </tr>
    </thead>
    <tbody>

    <template v-for="(film, index) in films">
      <tr>
        <td>{{ film }}</td>
        <td>
          <button @click="remove(index)" class="btn btn-danger">Usuń</button>
        </td>
      </tr>
      <td>
      </td>
    </template>
    </tbody>
    <tfoot>
    <tr>
      <td>Dopisz nowy film: <input v-model="film"></td>
      <td>
        <button @click="add()" class="btn btn-info">Dodaj</button>
      </td>
    </tr>
    </tfoot>
  </table>
  </body>

</template>

<style scoped>


</style>
