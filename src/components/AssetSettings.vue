<template>
  <v-row justify="center">
    <v-dialog
      width="1024"
    >
      <template v-slot:activator="{ props }">
        <v-btn
          color="primary"
          v-bind="props"
        >
        <v-icon icon="mdi-tune"></v-icon>
        </v-btn>
      </template>
      <v-card>
        <v-card-title>
          <span class="text-h5">{{ name_action }}</span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
              <v-select
                label="Ativo"
                :items="['EUR/ARG', 'BRL/USD', 'BRL/GPB', 'CHY/USD']"
              ></v-select>
              </v-col>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
              <v-text-field
                  label="Lance Inicial"
                  type="number"
                  required
                ></v-text-field>

              </v-col>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
                <v-text-field
                  label="Score"
                  type="number"
                  persistent-hint
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="2">
                <v-checkbox
                  label="Martin Gale"
                  required
                ></v-checkbox>
              </v-col>
              <v-col cols="4">
                <v-text-field
                  label="Sequencia Martin Gale"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="2">
                <v-checkbox
                  label="Soros"
                  required
                ></v-checkbox>
              </v-col>
              <v-col cols="4">
                <v-text-field
                  label="Sequencia Soros"
                  required
                ></v-text-field>
              </v-col>

              <v-col cols="2">
                <v-checkbox
                  label="Bolinger"
                  required
                ></v-checkbox>
              </v-col>
              <v-col cols="5">
                <v-text-field
                  label="Superior"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="5">
                <v-text-field
                  label="Inferior"
                  required
                ></v-text-field>
              </v-col>



            </v-row>
          </v-container>
          <small>*indicates required field</small>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="blue-darken-1"
            variant="text"
            @click="dialog = false"
          >
            Resetar Parâmetros
          </v-btn>
          <v-btn
            color="blue-darken-1"
            variant="text"
            @click="dialog = false"
          >
            Cancelar
          </v-btn>
          <v-btn
            color="blue-darken-1"
            variant="text"
            @click="dialog = false"
          >
            Salvar
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
export default {
 props: ['name_action']
}
</script>
