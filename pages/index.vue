<template>
  <div>
    <basic-section>
      <vueper-slides :fixed-height="true" :arrows="false">
        <vueper-slide v-for="(slide, i) in slides" :key="i" :title="slide.title">
          <template v-slot:content>
              <div class="vueperslide__content">
                <span>To take a trivial example, which of us ever undertakes laborious physical exercise, except to obtain some advantage from it?</span>
                <img src="~assets/wall (1).png" alt="" srcset="">
              </div>
          </template>
        </vueper-slide>
      </vueper-slides>
    </basic-section>
    
    <basic-section>
      <middle-section/>
    </basic-section>
    <basic-section>
      <div class="map-row">
        <div>
          <img class="map" src="~assets/map.png" alt="Map" srcset="">
        </div>
        <div class="empty"></div>
        <form>
          <v-container>
            <v-row>
                <v-col>
                <h2>
                  Contact Us
                </h2>
                <p>
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                </p>
                <v-text-field
                  outlined
                  rounded
                  v-model="fullName"
                  :error-messages="nameErrors"
                  label="Full Name"
                  required
                  @input="$v.fullName.$touch()"
                  @blur="$v.fullName.$touch()"
                ></v-text-field>
                <v-text-field
                  outlined
                  rounded
                  v-model="email"
                  :error-messages="emailErrors"
                  label="E-mail"
                  required
                  @input="$v.email.$touch()"
                  @blur="$v.email.$touch()"
                ></v-text-field>
                <v-text-field
                  rounded
                  outlined
                  v-model="email"
                  :error-messages="emailErrors"
                  label="Phone"
                  required
                  @input="$v.email.$touch()"
                  @blur="$v.email.$touch()"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-col>
                <v-select
                  outlined
                  rounded
                  v-model="selectCategory"
                  :items="items"
                  item-text="name"
                  item-value="categoryId"
                  :error-messages="selectErrors"
                  label="Category"
                  required
                  @change="$v.selectCategory.$touch()"
                  @blur="$v.selectCategory.$touch()"
                ></v-select>
              </v-col>
              <v-col>
                <v-select
                  outlined
                  rounded
                  :items="subCategories"
                  item-text="name"
                  item-value="subCategoryId"
                  :error-messages="selectErrors"
                  label="Subcategory"
                  required
                  @change="$v.select.$touch()"
                  @blur="$v.select.$touch()"
                ></v-select>
              </v-col>
              <v-col cols="12" sm="12">
                <v-textarea
                  outlined
                  v-model="message"
                  @change="$v.message.$touch()"
                  @blur="$v.message.$touch()"
                  :error-messages="messageErrors"
                  rounded
                  name="input-7-4"
                  label="Message"
                  :counter="100"
                ></v-textarea>
              </v-col>
              <v-col cols="12" sm="12">
                
                <span>
                  Please select at least one of the following:
                </span>
              </v-col>
            </v-row>
            <v-row>
              <v-col>
                <v-checkbox
                  v-model="checkbox1"
                  label="Option 1"
                  value="1"
                ></v-checkbox>
                <v-checkbox
                  v-model="checkbox2"
                  label="Option 2"
                  value="2"
                ></v-checkbox>
              </v-col>
            </v-row>
            <v-btn
              x-large
              rounded
              color="#4B00FF"
              dark
            >
              Submit
            </v-btn>
          </v-container>
          

        </form>
      </div>
      
    </basic-section>
    <home-footer/>
  </div>
</template>

<script>
  import {
    VueperSlides,
    VueperSlide
  } from 'vueperslides'
  import 'vueperslides/dist/vueperslides.css'
  import {
    validationMixin
  } from 'vuelidate'
  import {
    required,
    maxLength,
    email
  } from 'vuelidate/lib/validators'
  export default {
    components: {
      VueperSlides,
      VueperSlide
    },
    data() {
      return {
        slides: [{
            title: 'Slide #1',
            content: '<img src="/_nuxt/assets/wall (1).png" alt="" srcset="">'
          },
          {
            title: 'Slide #2',
          }
        ],
        valid: true,
        fullName:'',
        message:'',
        nameRules: [
          v => !!v || 'Name is required',
          v => (v && v.length <= 10) || 'Name must be less than 10 characters',
        ],
        email: '',
        emailRules: [
          v => !!v || 'E-mail is required',
          v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
        ],
        select: null,
        selectCategory: null,
        items: [
          'Item 1',
          'Item 2',
          'Item 3',
          'Item 4',
        ],
        checkbox1: false,
        checkbox2: false,
      }
    },
    methods:{
      Parse(data){
        let allSub = []
        let cat = []
        data.forEach((sub)=>{
          sub.subCategories && (allSub = allSub.concat(sub.subCategories))
        })

        return allSub;
      }
    },
    computed: {
      checkboxErrors () {
        const errors = []
        if (!this.$v.checkbox.$dirty) return errors
        !this.$v.checkbox.checked && errors.push('You must agree to continue!')
        return errors
      },
      selectErrors () {
        const errors = []
        if (!this.$v.select.$dirty) return errors
        !this.$v.select.required && errors.push('Item is required')
        return errors
      },
      nameErrors () {
        const errors = []
        if (!this.$v.fullName.$dirty) return errors
        !this.$v.fullName.required && errors.push('Name is required.')
        return errors
      },
      messageErrors () {
        const errors = []
        if (!this.$v.message.$dirty) return errors
        !this.$v.message.maxLength && errors.push('Message must be at most 100 characters long')
        !this.$v.message.required && errors.push('Message is required.')
        return errors
      },
      emailErrors () {
        const errors = []
        if (!this.$v.email.$dirty) return errors
        !this.$v.email.email && errors.push('Must be valid e-mail')
        !new RegExp('@spitogatos\.gr$').test(this.$v.email.$model) && errors.push('Must be valid e-mail')
        !this.$v.email.required && errors.push('E-mail is required')
        return errors
      },
      subCategories(){
        let exist = this.items.find(el=>el.categoryId == this.selectCategory);
        return exist ? exist.subCategories:[]
      }
    },
    mixins: [validationMixin],

    validations: {
      fullName: { required},
      message: { required, maxLength: maxLength(100) },
      email: { required, email },
      select: { required },
      selectCategory: { required },
      checkbox: {
        checked (val) {
          return val
        },
      },
    },
    async mounted(){
      let json = []
      try {
        let response = await fetch('https://run.mocky.io/v3/0b8fbded-6ce4-4cb2-bf2f-d2c39207506b', {
          method: 'GET', // or 'PUT'
        })
        json = await response.json()
        let allSubs = this.Parse(json);
        json[0].subCategories = allSubs;
      } catch (error) {
        
      }
      
      this.items = json;

      
    }
  }
</script>

<style>
  .vueperslides,
  .vueperslide__content,
  .vueperslide__content img {
    width: 100vw;
    height: 100vh;
  }
  .thin {
    text-decoration-line: underline;
    text-decoration-style: solid;
    text-decoration-color: red;
    text-decoration-thickness: 1px;
  }
  .vueperslide__content span {
    top: 50%;
    left: 10%;
    position: absolute;
    text-align: left;
    font: normal normal 800 30px/40px Montserrat;
    max-width: 30%;
    color: white;
  }

  .map{
    width:100%;
    height: 100%;
  }

  form button{
        width: 50%;
    margin-left: 25%;
  }
  .v-input.v-input--checkbox{
    display: inline-block;
    margin-right: 10px;
  }

  .map-row {
    display: flex;
    background-color: var(--white-darke-2);
  }

  .map-row form{
    flex-basis: 75%;
    padding-right: 100px;
    min-height: 100vh;
  }

  .empty{
    flex-basis:20%
  }
</style>