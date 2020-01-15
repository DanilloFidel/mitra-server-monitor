<template>
  <v-app>
    <v-container fluid class="container">
      <v-card class="card">
        <img src="./assets/hqdefault.jpg" />
        <div class="content" style="height: 45%; width: 100%;">
          <v-progress-linear indeterminate color="green darken-2"></v-progress-linear>
          <div>
            <h5>Memória</h5>
          <v-simple-table dense>
            <template v-slot:default>
              <thead>
                <tr>
                  <th class="text-left">Total</th>
                  <th class="text-left">Em uso</th>
                  <th class="text-left">Disponível</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="(item, idx) in ramStatus" :key="idx">
                  <td>{{ item.all + 'GB' }}</td>
                  <td>{{ item.used }}</td>
                  <td>{{ item.free }}</td>
                </tr>
              </tbody>
            </template>
          </v-simple-table>
          </div>
        </div>
        <div style="height: 5%" class="btn-box">
          <v-btn small color="yellow">reiniciar</v-btn>
          <v-btn small color="red">derrubar</v-btn>
          <v-btn small color="green">subir</v-btn>
        </div>
      </v-card>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    ramStatus: [{ all: 15, used: 7, free: 8 }]
    //
  })
};
</script>

<style scoped>
.container {
  background-color: lightslategray;
  widows: 100vw;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
}
.card {
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  height: 100%;
  padding: 10px;
}
.btn-box {
  display: flex;
  width: 100%;
  justify-content: space-around;
}
.content{
  display: flex;
  flex-direction: column;
  justify-content: space-around
}
</style>
