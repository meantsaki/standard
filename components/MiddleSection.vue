<template>
  <v-container>
      <v-row>
          <v-col col="12" md="7">
              <img class="face" src="~assets/face_small (1).png" alt="" srcset="">
          </v-col>
          <v-col col="12" md="5">
              <div class="above-title">
                  Since the 1500s
              </div>
              <h3 class="title-standard">
                  The standard
              </h3>
              <p class="description">
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt.
              </p>
          </v-col>
      </v-row>
      <v-row style="padding-bottom:200px">
          <v-col col="12" md="7">
              <div class="above-title">
                  Since the 1500s
              </div>
              <h3 class="title-standard">
                  The standard
              </h3>
              <p class="description">
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </p>
          </v-col>
          <v-col col="12" md="5">
               <img class="pillow" src="~assets/pillow.png" alt="" srcset="">
          </v-col>
      </v-row>
  </v-container>
</template>

<script>
export default {

}
</script>

<style>
.above-title{
font: normal normal bold 16px/19px Montserrat;
color: #CFCFCF;
margin-top:50px;
}

.title-standard{
    font: normal normal 800 32px/39px Montserrat;
    margin-bottom:30px;
}

img.face{
    text-align: right;
    width: 80%;
}

.description{
    width: 75%;
}

img.pillow{
    transition: 0.70s;
}

img.pillow:hover{
  transform: rotate(180deg);
}
</style>