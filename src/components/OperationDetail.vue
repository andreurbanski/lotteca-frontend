<template class="w-100 h-100">
  <v-table
    fixed-header
    class="w-100 h-100"
  >
    <thead>
      <tr>
        <th class="text-left">
          Ativo
        </th>
        <th class="text-left">
          RSI
        </th>
        <th class="text-left">
          MME (100)
        </th>
        <th class="text-left">
          MME (200)
        </th>
        <th class="text-left">
          Sequência
        </th>
        <th class="text-left">
          Elefante
        </th>
        <th class="text-left">
          Bolinger
        </th>
        <th class="text-left">
          Score
        </th>
        <th class="text-left" colspan="3">
          Ações
        </th>
      </tr>
    </thead>
    <tbody>
      <tr
        v-for="item in bots"
        :key="item.name"
      >
      <td>{{ item.assets[0].name }}</td>
      <td>{{ item.rsi }}</td>
      <td>{{ item.elefante }}</td>
      <td>{{ item.mme100 }}</td>
      <td>{{ item.mme200 }}</td>
      <td>{{ item.bolinger }}</td>
      <td>{{ item.sequencia }}</td>
      <td>{{ item.score }} (3.5)</td>
      <td><AssetSettings name_action="Edit Bot"></AssetSettings></td>
      <td> <v-switch
          color="success"
          value="John"
          hide-details
        ></v-switch>
      </td>
      </tr>
    </tbody>
  </v-table>
</template>

<script>
import AssetSettings from './AssetSettings.vue';

  export default {
    data() {
        return {
            bots: [],
        };
    },
    methods: {
      fetchBots() {
        fetch('http://192.168.15.122:8000/api/bot/list', {
        method: "GET",
        headers: {},
      })
        .then((response) => {
          response.json().then((data) => {
            this.bots = data;
          });
        })
        .catch((err) => {
          console.error(err);
        });
      }
    },
    created() {
      this.fetchBots();
    },
    components: { AssetSettings }
}
</script>
