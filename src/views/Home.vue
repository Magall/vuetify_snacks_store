<template>
  <div class="home">
    <v-container>
      <v-row justify="center">
        <v-col cols="12" md="12" lg="12">
          <p class="headline" align-self="center">Mais Pedidos</p>
        </v-col>
      </v-row>
      <v-row justify="center" align="center">
        <v-col :key="index" md="3" lg="3" v-for="(s,index) in topSeller">
          <v-card class="mx-auto" max-width="400">
            <v-img class="white--text align-end" height="300px" :src="require('@/assets/' + s.img)">
              <v-card-title>{{s.title}}</v-card-title>
            </v-img>
            <v-card-text class="text--primary">
              <div>{{s.subTitle}}</div>
              <div>{{s.price}}</div>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>

      <div id="cardapio">
        <v-row justify="center">
          <v-col cols="12" md="5" lg="5" xl="9">
            <p class="headline" align-self="center">Cardápio</p>
            <v-list>
              <CardapioItem
                :burger="item.burger"
                :price="item.price"
                :ingredients="item.ingredients"
                :key="i"
                :img="item.img"
                v-for="(item,i) in cardapio"
              />
            </v-list>
          </v-col>
        </v-row>
      </div>
      <div id="unidades">
        <v-row>
          <v-col cols="12" md="12" lg="12">
            <p class="headline" align-self="center">Unidades</p>
          </v-col>
        </v-row>
        <v-row justify="center">
          <v-col cols="9" md="5">
            <v-card class="mx-auto" max-width="400">
              <v-img class="white--text align-end" height="200px" src="@/assets/caicarajpg.jpg"></v-img>

              <v-card-subtitle class="pb-0">Caiçara</v-card-subtitle>

              <v-card-text class="text--primary">
                <div>3424-5555</div>

                <div>Rua Minerva nº45, Caiçara</div>
              </v-card-text>
            </v-card>
          </v-col>

          <v-col cols="12" md="5">
            <v-card class="mx-auto" max-width="400">
              <v-img class="white--text align-end" height="200px" src="@/assets/contagem.jpg"></v-img>

              <v-card-subtitle class="pb-0">3222-1111</v-card-subtitle>

              <v-card-text class="text--primary">
                <div>Contagem</div>

                <div>Rua Toureiro, nº45</div>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </div>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src
//import CardapioItem from "./../components/Cardapio/CardapioItem";
export default {
  name: "Home",
  components: { CardapioItem : () =>import("./../components/Cardapio/CardapioItem.vue") },
  data() {
    return {
      dialog: false,
      cardapio: [
        {
          burger: "T-Chicken",
          price: "27.50",
          ingredients:
            "Pão com gergelim, hambúrguer artesanal de frango empanado, queijo muçarela, picles de cebola, salada cremosa de repolho e molho de mostarda e mel.",
          img: "t-hot.jpg"
        },
        {
          burger: "T-Burger",
          price: "17.90",
          ingredients:
            "Pão com gergelim, hambúrguer artesanal de 160g, queijo, alface, tomate e molho maionese Tchambows.",
          img: "t-hot.jpg"
        },
        {
          burger: "T-DDT",
          price: "31.90",
          ingredients:
            "Esse hambúrguer é preparado com delicioso pão australiano, hambúrguer artesanal de 160g, duas fatias de cheddar, cebolas enroladas em tiras de bacon, alface americana, tomate e a saborosa maionese Tchambows. Acompanhamento de fritas.",
          img: "t-hot.jpg"
        },
        {
          burger: "T-Egg-Bacon",
          price: "20.90",
          ingredients:
            "Pão com gergelim, hambúrguer artesanal de 160g, bacon, ovo, queijo, alface, tomate e molho maionese Tchambows.",
          img: "t-hot.jpg"
        },
        {
          burger: "T-Hot",
          price: "27.50",
          ingredients:
            "Pão com gergelim, hambúrguer artesanal de 160g, queijo provolone, queijo muçarela, pimenta jalapeño chapeada, bacon, picles de cebola e geleia de pimenta.",
          img: "t-hot.jpg"
        },
        {
          burger: "T-Paradise",
          price: "29.50",
          ingredients:
            "Pão com gergelim, 2 hambúrgueres artesanais de 160g, bacon crocante, duas fatias de cheddar, cebola roxa chapeada, picles de pepino e molho barbecue.",
          img: "t-paradisejpg.jpg"
        },
        {
          burger: "T-smash",
          price: "20.00",
          ingredients:
            "Deleicioso Burger de 120 gramas cebola caramelizada e queijo chedar",
          img: "t-burger-1.jpg"
        },
        {
          burger: "T-Uai",
          price: "28.50",
          ingredients:
            "Elaborado com ingredientes tipicamente mineiros, o Tchambows UAI leva pão de hambúrguer com gergelim, carne artesanal de 160g, queijo Minas derretido, crispy de couve, bacon caramelizado no melado de cana e o sensacional molho maionese de alho. Acompanhamento de fritas.",
          img: "t-uaipg.jpg"
        },
        {
          burger: "T-Sundae",
          price: "15.90",
          ingredients:
            "Sorvete de chocolate ou creme na taça com calda de chocolate e paçoca.",
          img: "t-sundae.jpg"
        }
      ],
      topSeller: [
        {
          title: "T-smash",
          subTitle: "Muito Chedar pra você",
          price: "R$16,00",
          img: "t-burger-1.jpg"
        },
        {
          title: "T-Hot",
          subTitle: "Muita Pimenta pra você",
          price: "R$16,00",
          img: "t-hot.jpg"
        },
        {
          title: "T-DDT",
          subTitle: "Muito Bacon pra você",
          price: "R$16,00",
          img: "t-ddt.jpg"
        }
      ]
    };
  }
};
</script>
