<template>
  <v-list-item>
    <span>{{burger}}</span>
    <v-spacer></v-spacer>
    <div class="text-center">
      <v-dialog v-model="dialog" width="500">
        <template v-slot:activator="{ on }">
          <v-btn color="#c62828" dark v-on="on" aria-label="Mostrar Ingredientes">
            <v-icon>list</v-icon>
          </v-btn>
        </template>
        <v-card>
          <v-card-title max-width="600" class="headline grey lighten-2" primary-title>Ingredientes</v-card-title>
          <v-container>
            <v-row>
              <v-col cols="3" lg="5">
                <v-img role="img" :src="require('@/assets/' + img)"></v-img>
              </v-col>
              <v-col>
                <v-card-text>{{ingredients}}</v-card-text>
              </v-col>
            </v-row>
          </v-container>
          <v-divider></v-divider>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="primary" text @click="dialog = false" aria-label="ok">Ok</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </div>
    <span class="ml-4">R${{price}}</span>
  </v-list-item>
</template>
<script>
export default {
  name: "CardapioItem",
  data() {
    return {
      dialog: false
    };
  },
  props: {
    burger: String,
    ingredients: String,
    price: String,
    img: String
  }
};
</script>