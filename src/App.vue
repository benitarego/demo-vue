<template>
  <v-app>
    <v-app-bar app class="pa-1 black">
      <v-app-bar-nav-icon color="grey" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-img contain height="20" src="@/assets/N.png"></v-img>
      <v-img contain height="20" src="@/assets/O.png"></v-img>
      <v-img contain height="20" src="@/assets/V.png"></v-img>
      <v-img contain height="20" src="@/assets/A.png"></v-img>
    
      <v-spacer></v-spacer>
      
      <p class="mt-4 font-weight-thin white--text" style="font-family: 'Roboto'; font-size: 20px;">Tanay</p>
      
      <v-btn small color="black"><v-icon color="white">mdi-chevron-down</v-icon></v-btn>
      
      <v-btn color="black"><v-icon color="white" size="30">mdi-cart-outline</v-icon></v-btn>
    </v-app-bar>

    <v-main class="pa-6 black">

      <v-divider light class="mt-16 grey"></v-divider>
      
      <v-carousel class="mt-12"
        :continuous="false"
        :cycle="cycle"
        :show-arrows="false"
        hide-delimiter-background
        delimiter-icon="mdi-minus">
        <v-carousel-item v-for="(slide, i) in slides" :key="i">
          <v-sheet :color="colors[i]" height="100%" tile>
            <v-row
              class="fill-height"
              align="center"
              justify="center"
            >
              <h1 class="font-weight-light">{{ slide }}</h1>
            </v-row>
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
      
      <h1 style="font-family: 'Roboto';" class="font-weight-bold mt-8 white--text">Everyday rinse and reload</h1>
      <p class="mt-2 grey--text font-weight-light">Achieve your dream skin goal with this complete package of skincare products that will rejuvenate your day.</p>
      
      <v-row class="ml-1 my-2">
        <v-chip color="#079741">
          <v-rating
            v-model="rating"
            color="#DADADA"
            dense
            half-increments
            hover
            size="10">
          </v-rating>
        </v-chip>

        <h4 class="grey--text text--lighten-2 ml-3 my-1">{{ rating }}</h4>

        <h4 class=" mt-1 ml-3 grey--text">Click to read reviews ></h4>
        <h1 class="pa-2 my-4 font-weight-black white--text">$ 899</h1>
        <h1 class="pa-2 my-4 font-weight-light grey--text text-decoration-line-through">$ 1299</h1>
      </v-row>

      <v-col>
        <v-card height="100%" width="100%" style="border-radius: 10px;" color="#21272C">
          <v-col>
            <v-chip color="#067BD8" x-small>
              <v-icon x-small color="white">mdi-star</v-icon>
              <p class="ma-2 mt-2 white--text">MOST POPULAR</p>
              <v-icon x-small color="white">mdi-star</v-icon>
            </v-chip>
            <v-row>
              <h4 class="ml-3 mt-4 font-weight-bold white--text">3 Months Pack(4 tubes)</h4>
              <v-spacer></v-spacer>
              <h2 class="mr-3 mt-3 font-weight-regular white--text" style="font-family: 'DM Serif Display'">$595</h2>
            </v-row>
            <v-row>
              <h4 class="ml-3 font-weight-light grey--text">Savings: $ 200</h4>
              <v-spacer></v-spacer>
              <h2 class="mr-3 font-weight-light grey--text text-decoration-line-through" style="font-family: 'DM Serif Display'">$795</h2>
            </v-row>
            <v-row>
              <p class="ml-3 green--text">38% Saved</p>
              <p class="ml-3 orange--text">Best Results</p>
            </v-row>
          </v-col>
        </v-card>

        <v-card class="mt-4" height="100%" width="100%" style="border-style: solid; border: 2px solid white; border-radius: 10px;" color="#374B5B" outlined>
          <v-col>
            <v-row>
              <h4 class="ml-3 mt-4 font-weight-bold white--text">3 Months Pack(4 tubes)</h4>
              <v-spacer></v-spacer>
              <h2 class="mr-3 mt-3 font-weight-bold white--text" style="font-family: 'DM Serif Display'">$899</h2>
            </v-row>
            <v-row>
              <h4 class="ml-3 font-weight-light #28333D--text">Savings: $ 100</h4>
              <v-spacer></v-spacer>
              <h2 class="mr-3 font-weight-light #28333D--text text-decoration-line-through" style="font-family: 'DM Serif Display'">$999</h2>
            </v-row>
            <v-row>
              <p class="ml-3 green--text">12% Saved</p>
            </v-row>
          </v-col>
        </v-card>

        <v-btn class="mt-6" width="100%" color="#13324A" depressed>
          <v-icon color="grey">mdi-cart-outline</v-icon>
          <p class="pa-2 mt-4 white--text">ADD TO CART</p>
        </v-btn>
      </v-col>
    </v-main>
    
    <v-main class="black pa-2">
      <v-col>
        <h3 style="font-family: 'Belgrano'; size: 12px;" class="mt-4 headline grey--text text-center">Curated by 
          experts, we've created an essential line of skin, body and hair products for men. From head to toe, we've got 
          you covered.</h3>
        <h3 style="font-family: 'Belgrano'; size: 12px;" class="mb-8 headline grey--text text-center">Finally.</h3>
        
        <v-divider light class=" mt-6 white"></v-divider>

        <v-expansion-panels v-model="panel" flat tile>
          <v-expansion-panel style="background: black">
            <v-expansion-panel-header class="white--text">Benefit 1
              <template v-slot:actions>
                <v-icon color="white">mdi-plus</v-icon>
              </template>
            </v-expansion-panel-header>
            <v-expansion-panel-content class="grey--text">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit.
              Maecenas non blandit orci. Nulla cursus justo eget sem
              viverra faucibus. Pellentesque eu mi nibh. Pellentesque et
              bibendum purus, tempus sollicitudin ligula. Donec
              eleifend mi nec ipsum molestie, at pulvinar elit congue.
              Phasellus fermentum tortor vel sagittis tristique. Ut
              molestie lorem quis arcu tincidunt accumsan.
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>

        <v-divider light class="white"></v-divider>

        <v-expansion-panels v-model="panel" flat tile>
        <v-expansion-panel style="background: black">
          <v-expansion-panel-header class="white--text">Benefit 2
            <template v-slot:actions>
              <v-icon color="white">mdi-plus</v-icon>
            </template>
          </v-expansion-panel-header>
          <v-expansion-panel-content class="grey--text">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            Maecenas non blandit orci. Nulla cursus justo eget sem
            viverra faucibus. Pellentesque eu mi nibh. Pellentesque et
            bibendum purus, tempus sollicitudin ligula. Donec
            eleifend mi nec ipsum molestie, at pulvinar elit congue.
            Phasellus fermentum tortor vel sagittis tristique. Ut
            molestie lorem quis arcu tincidunt accumsan.
          </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>

        <v-divider light class="white"></v-divider>
      </v-col>
    </v-main>

    <div id="fadeTop">
      <v-img height="700px" width="100%" src="@/assets/back.png">
        <h1 class=" pt-5 font-weight-bold white--text text-center">Picked up from the himalayas</h1>
        <h3 class="mt-3 pa-3 font-weight-light grey-darken--text text-center">Curated by experts, we’ve created an
        essential line of skin, body and hair
        products for men. From head to toe,
        we’ve got you covered. Finally.</h3>
      </v-img>
    </div>

  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        rating: 4.5,
        colors: [
          'green',
          'grey',
          'yellow',
          'red',
          'orange',
        ],
        cycle: false,
        slides: [
          'Slide 1',
          'Slide 2',
          'Slide 3',
          'Slide 4',
          'Slide 5',
        ],
      }
    },
  }
</script>

<style scoped>
</style>
