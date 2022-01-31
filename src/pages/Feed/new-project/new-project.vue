<template>
  <v-dialog width="1000" :value="value" persistent>
    <v-card>
      <v-toolbar dark color="primary">
        <v-toolbar-title>Novo projeto</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn icon dark @click="closeModal">
          <v-icon>mdi-close</v-icon>
        </v-btn>
      </v-toolbar>
      <v-card-text>
        <v-container fluid pa-4>
          <v-row>
            <v-col cols="4">
              <v-text-field
                label="Nome do projeto"
                hide-details="auto"
              ></v-text-field>
            </v-col>
            <v-col cols="3">
              <v-text-field
                v-model="maxMembers"
                label="Número máximo de membros"
                :rules="numberRules"
                type="number"
              ></v-text-field>
            </v-col>
            <v-col cols="5">
              <v-radio-group v-model="radioGroup" row>
                <v-radio
                  v-for="n in stageProject"
                  :key="n"
                  :label="n"
                  :value="n"
                ></v-radio>
              </v-radio-group>
            </v-col>
            <v-col cols="12">
              <v-autocomplete
                v-model="friends"
                :items="people"
                filled
                chips
                color="blue-grey lighten-2"
                label="Escolha a(s) tecnologia(s)"
                item-text="name"
                item-value="name"
                multiple
              >
                <template v-slot:selection="data">
                  <v-chip
                    v-bind="data.attrs"
                    :input-value="data.selected"
                    close
                    @click="data.select"
                    @click:close="remove(data.item)"
                  >
                    {{ data.item.name }}
                  </v-chip>
                </template>
              </v-autocomplete>
            </v-col>
          </v-row>
          <v-row>
            <v-textarea
              counter
              label="Breve descrição do seu projeto"
              rows="3"
            ></v-textarea>
          </v-row>
        </v-container>
      </v-card-text>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn color="error" outlined @click="closeModal">
          <v-icon left>mdi-close</v-icon>
          Cancelar
        </v-btn>
        <v-btn color="success" outlined>
          <v-icon left>mdi-content-save</v-icon>
          Salvar
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>
<script>
export default {
  data() {
    return {
      maxMembers: 1,
      radioGroup: 1,
      dialog: false,
      friends: null,
      stageProject: ["Início", "Em andamento", "Reta final"],
      people: [{ name: "Forex" }, { name: "Javascript" }, { name: "Java" }],
      numberRules: [
        (v) => v > 0 || "O valor não pode ser menor ou igual a zero",
      ],
    };
  },
  props: {
    value: {
      type: Boolean,
      default: () => false,
    },
  },
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>
<style lang="scss" scoped></style>
