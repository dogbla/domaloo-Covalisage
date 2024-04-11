<template>
  <div class="bg-yellow-400 p-4 mt-4  relative h-64">
    <div class="flex justify-center  ">
      <div class="mt-5 text-center">
        <p class="text-white font-bold">Domaloo Covalisage!</p>
        <p class="text-white">Envoie de colis
          <br> <span class="text-black">facile, sûr et rapide</span><br>
          <span>visitez domaloo--market.com</span>
        </p>
      </div>
    </div>
    <div class="container mx-auto">
      <!-- <img src="/img/logo-domalo.jpg" style="height: 150px;width: 150px;margin-top: -100px;" alt=""> -->
      <div class="flex justify-center">

        <div class="grid grid-cols-1 gap-4 w-[800px]">

          <div class="h-96 bg-white p-4 relative overflow-visible rounded-lg mt-12 border border-gray-300">
            <!-- Ajout des chiffres -->
            <div class="flex justify-between items-center">
              <!-- Première étape -->
              <div class="flex items-center justify-center w-8 h-8 bg-orange-400 text-white rounded-full mx-2">
                1
              </div>
              <div class="h-2 bg-gradient-to-r from-orange-400 to-gray-300 flex-grow rounded-full relative">
                <div class="h-full bg-orange-400 flex-grow rounded-full"
                  :style="{ width: (step === 1 ? '50%' : step > 1 ? '100%' : '0%') }">
                </div>
              </div>
              <!-- Deuxième étape -->
              <div class="flex items-center justify-center w-8 h-8 bg-gray-300 text-white rounded-full mx-2"
                :class="{ 'bg-orange-400': step >= 2 }" @click="step = 2">2
              </div>
              <div class="h-2 bg-gradient-to-r from-gray-300 to-gray-300 flex-grow rounded-full relative">
                <div class="h-full bg-orange-400 flex-grow rounded-full"
                  :style="{ width: (step === 2 ? '50%' : step > 2 ? '100%' : '0%') }"></div>
              </div>
              <!-- Troisième étape -->
              <div class="flex items-center justify-center w-8 h-8 bg-gray-300 text-white rounded-full mx-2"
                :class="{ 'bg-orange-400': step >= 3 }" @click="step = 3">3
              </div>
              <div class="h-2 bg-gradient-to-r from-gray-300 to-gray-300 flex-grow rounded-full relative">
                <div class="h-full bg-orange-400 flex-grow rounded-full"
                  :style="{ width: (step === 3 ? '50%' : step > 3 ? '100%' : '0%') }"></div>
              </div>
              <!-- Quatrième étape -->
              <div class="flex items-center justify-center w-8 h-8 bg-gray-300 text-white rounded-full mx-2"
                :class="{ 'bg-orange-400': step >= 4 }" @click="step = 4">4
              </div>
            </div>



            <hr class="mt-5">

            <div>


              <form @submit.prevent="submitForm">
                <div>
                  <div v-if="step === 1">
                    <h3 class="font-bold">Vos informations</h3>
                    <p class="text-gray-500">Si vous avez déjà commandé chez Domaloo, <a href=""
                        class="text-orange-500">cliquez
                        ici</a></p>
                    <!-- Première étape du formulaire -->
                    <div class="w-full flex flex-wrap justify-between">
                      <div class="w-full lg:w-5/12 px-4 mb-4 lg:mb-0 mt-5">
                        <label for="username" class="block text-gray-700 font-semibold">Nom
                          complet</label>
                        <div class="relative">
                          <input v-model="formData.user_name" type="text" id="username" placeholder="John Carter"
                            class="w-full border border-gray-300 rounded-full p-2 pr-10 outline-none" />
                          <svg xmlns="http://www.w3.org/2000/svg"
                            class="h-6 w-6 absolute right-3 top-1/2 transform -translate-y-1/2 text-gray-400"
                            viewBox="0 0 20 20" fill="currentColor">
                            <path fill-rule="evenodd" d="M10 12a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd" />
                            <path fill-rule="evenodd"
                              d="M4.293 8.293a1 1 0 011.414 0L10 12.586l4.293-4.293a1 1 0 111.414 1.414l-5 5a1 1 0 01-1.414 0l-5-5a1 1 0 010-1.414zM4 5a3 3 0 100 6 3 3 0 000-6z"
                              clip-rule="evenodd" />
                          </svg>
                        </div>
                      </div>
                      <div class="w-full lg:w-5/12 px-4 mb-4 lg:mb-0 mt-5">
                        <label for="user_email" class="block text-gray-700 font-semibold">Email</label>
                        <div class="relative">
                          <input v-model="formData.user_email" type="email" id="email" placeholder="Email adress"
                            class="w-full border border-gray-300 rounded-full p-2 pr-10 outline-none" />
                          <svg xmlns="http://www.w3.org/2000/svg"
                            class="h-6 w-6 absolute right-3 top-1/2 transform -translate-y-1/2 text-gray-400"
                            viewBox="0 0 20 20" fill="currentColor">
                            <path fill-rule="evenodd" d="M10 12a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd" />
                            <path fill-rule="evenodd"
                              d="M4.293 8.293a1 1 0 011.414 0L10 12.586l4.293-4.293a1 1 0 111.414 1.414l-5 5a1 1 0 01-1.414 0l-5-5a1 1 0 010-1.414zM4 5a3 3 0 100 6 3 3 0 000-6z"
                              clip-rule="evenodd" />
                          </svg>
                        </div>
                      </div>

                      <div class="w-full lg:w-5/12 px-4 mt-5">
                        <label for="phone" class="block text-gray-700 font-semibold">Numéro de
                          téléphone</label>
                        <div class="relative">
                          <input v-model="formData.user_phone" type="tel" id="phone" placeholder="(123) 456 - 7890"
                            class="w-full border border-gray-300 rounded-full p-2 pr-10 outline-none" />
                          <svg xmlns="http://www.w3.org/2000/svg"
                            class="h-6 w-6 absolute right-3 top-1/2 transform -translate-y-1/2 text-gray-400"
                            viewBox="0 0 20 20" fill="currentColor">
                            <path fill-rule="evenodd"
                              d="M13.061 1.939A10 10 0 0 0 2.121 12.88l6.011 6.011a1 1 0 0 0 1.414 0l6.011-6.011a10 10 0 0 0-7.495-17.061zM10 7a3 3 0 1 0 0 6 3 3 0 0 0 0-6z"
                              clip-rule="evenodd" />
                          </svg>
                        </div>
                      </div>
                    </div>



                    <button @click="nextStep"
                      class="mt-28 bg-orange-500 hover:bg-orange-700 text-white font-bold py-2 px-4 rounded-full float-right">
                      Suivant
                    </button>

                  </div>
                  <div v-else-if="step === 2">
                    <h3 class="font-bold">Mode de transport</h3>
                    <p class="text-gray-500">Choisissez le mode de transport qui vous convienne</p>
                    <!-- Deuxième étape du formulaire -->

                    <div class="mt-5 container mx-auto">
                      <div class="grid grid-cols-1 lg:grid-cols-2 gap-4">
                        <!-- Case 1 -->
                        <label :class="{ 'border-orange-500': transport_mode === 'covalisage' }"
                          class="border p-4 flex items-center justify-center rounded cursor-pointer"
                          @click="selectOption('covalisage')">
                          <input type="radio" name="shipping" class="hidden" checked>
                          <div class="w-10 h-10 bg-orange-100 rounded-full flex items-center justify-center mr-3">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-orange-400" viewBox="0 0 20 20"
                              fill="currentColor">
                              <path fill-rule="evenodd" d="M10 12a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd" />
                              <path fill-rule="evenodd"
                                d="M4.293 8.293a1 1 0 011.414 0L10 12.586l4.293-4.293a1 1 0 111.414 1.414l-5 5a1 1 0 01-1.414 0l-5-5a1 1 0 010-1.414zM4 5a3 3 0 100 6 3 3 0 000-6z"
                                clip-rule="evenodd" />
                            </svg>
                          </div>
                          <div class="text-center flex flex-col items-center">
                            <span class="text-lg font-semibold text-orange-500 font-bold">Co-valisage</span>
                            <span class="text-sm text-gray-400 mt-1">2 - 7 jours</span>
                          </div>
                        </label>

                        <!-- Case 2 -->
                        <label :class="{ 'border-orange-500': transport_mode === 'groupage' }"
                          class="border p-4 flex items-center justify-center rounded cursor-pointer"
                          @click="selectOption('groupage')">
                          <input type="radio" name="shipping" class="hidden">
                          <div class="w-10 h-10 bg-orange-100 rounded-full flex items-center justify-center mr-3">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-orange-400" viewBox="0 0 20 20"
                              fill="currentColor">
                              <path fill-rule="evenodd" d="M10 12a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd" />
                              <path fill-rule="evenodd"
                                d="M4.293 8.293a1 1 0 011.414 0L10 12.586l4.293-4.293a1 1 0 111.414 1.414l-5 5a1 1 0 01-1.414 0l-5-5a1 1 0 010-1.414zM4 5a3 3 0 100 6 3 3 0 000-6z"
                                clip-rule="evenodd" />
                            </svg>
                          </div>
                          <div class="text-center flex flex-col items-center">
                            <span class="text-lg font-semibold text-orange-500 font-bold">Groupage maritime</span>
                            <span class="text-sm text-gray-400 mt-1">30 - 40 jours</span>
                          </div>
                        </label>
                      </div>
                    </div>
                    <div class="mt-5 w-full flex flex-wrap justify-between">
                      <div class="w-full lg:w-5/12 px-4 mb-4 lg:mb-0">
                        <label for="username" class="block text-gray-700 font-semibold">Adresse
                          de Départ</label>
                        <div class="relative">
                          <select v-model="formData.departure_adress" name="" id=""
                            class="w-full border border-gray-300 rounded-full p-2 pr-10 outline-none">
                            <option value="">Adresse de départ</option>
                            <option value="Lomé">Lomé, rue Moyama</option>
                            <option value="Paris">Paris, rue cocotier</option>
                          </select>

                        </div>
                      </div>
                      <div class="w-full lg:w-5/12 px-4 mb-4 lg:mb-0">
                        <label for="username" class="block text-gray-700 font-semibold">Adresse
                          de
                          livraison</label>
                        <div class="relative">
                          <select v-model="formData.arrival_adress" name="" id=""
                            class="w-full border border-gray-300 rounded-full p-2 pr-10 outline-none">
                            <option value="">Adresse livraison</option>
                            <option value="Lomé">Lomé, rue Moyama</option>
                            <option value="Paris">Paris, rue cocotier</option>
                          </select>

                        </div>
                      </div>



                    </div>
                    <button @click="prevStep"
                      class="mt-24 bg-white-500 hover:bg-white-700 text-orange-500 font-bold py-2 px-4 rounded-full border border-orange-500">
                      Précédent
                    </button>

                    <button @click="nextStep"
                      class="float-right mt-24 bg-orange-500 hover:bg-orange-700 text-white font-bold py-2 px-4 rounded-full">
                      Suivant
                    </button>
                  </div>
                  <div v-else-if="step === 3">
                    <!-- Troisième étape du formulaire -->
                    <h3 class="font-bold">Décrivez-nous votre colis</h3>
                    <p class="text-gray-500">Choisissez une taille</p>

                    <div class="mt-5 container mx-auto">
                      <div class="grid grid-cols-1 lg:grid-cols-3 gap-4">
                        <!-- Case 1 -->
                        <div
                          :class="{ 'border-orange-500': formData.package_category === 'Petit colis', 'border': true, 'p-4': true, 'flex': true, 'items-center': true, 'justify-center': true }">
                          <div class="w-5 h-5  rounded-full flex items-center justify-center mr-3">
                            <input type="radio" id="radio1" name="radio" class=""
                              @change="selectTailleColis('Petit colis')" v-model="formData.package_category"
                              value="Petit colis">
                          </div>
                          <div class="text-center flex flex-col items-center">
                            <span class="text-lg font-semibold ">Petit colis</span>
                          </div>
                        </div>

                        <!-- Case 2 -->
                        <div
                          :class="{ 'border-orange-500': formData.package_category === 'Colis moyen', 'border': true, 'p-4': true, 'flex': true, 'items-center': true, 'justify-center': true }">
                          <div class="w-5 h-5 bg-gray-100 rounded-full flex items-center justify-center mr-3">
                            <input type="radio" id="radio2" name="radio" class=""
                              @change="selectTailleColis('Colis moyen')" v-model="formData.package_category"
                              value="Colis moyen">
                          </div>
                          <div class="text-center flex flex-col items-center">
                            <span class="text-lg font-semibold ">Colis moyen</span>
                          </div>
                        </div>

                        <!-- Case 3 -->
                        <div
                          :class="{ 'border-orange-500': formData.package_category === 'Gros paquet', 'border': true, 'p-4': true, 'flex': true, 'items-center': true, 'justify-center': true }">
                          <div class="w-5 h-5 bg-gray-100 rounded-full flex items-center justify-center mr-3">
                            <input type="radio" id="radio3" name="radio" class=""
                              @change="selectTailleColis('Gros paquet')" v-model="formData.package_category"
                              value="Gros paquet">
                          </div>
                          <div class="text-center flex flex-col items-center">
                            <span class="text-lg font-semibold ">Gros paquet</span>
                          </div>
                        </div>
                      </div>
                    </div>

                    <div class="mt-5 w-full flex flex-wrap justify-between">
                      <div class="w-full lg:w-5/12 px-4 mb-4 lg:mb-0">
                        <label for="package_value" class="block text-gray-700 font-semibold">Valeur du colis (F CFA)
                        </label>
                        <div class="relative">
                          <input v-model="formData.package_value" type="text" id="valeurColis" placeholder="26.000 FCFA"
                            class="w-full border border-gray-300 rounded-full p-2 pr-10 outline-none" />
                          <svg xmlns="http://www.w3.org/2000/svg"
                            class="h-6 w-6 absolute right-3 top-1/2 transform -translate-y-1/2 text-gray-400"
                            viewBox="0 0 20 20" fill="currentColor">
                            <path fill-rule="evenodd" d="M10 12a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd" />
                            <path fill-rule="evenodd"
                              d="M4.293 8.293a1 1 0 011.414 0L10 12.586l4.293-4.293a1 1 0 111.414 1.414l-5 5a1 1 0 01-1.414 0l-5-5a1 1 0 010-1.414zM4 5a3 3 0 100 6 3 3 0 000-6z"
                              clip-rule="evenodd" />
                          </svg>
                        </div>
                      </div>
                      <div class="w-full lg:w-5/12 px-4 mb-4 lg:mb-0">
                        <label for="poids" class="block text-gray-700 font-semibold">Ajoutez un poids (Kg)</label>
                        <div class="relative">
                          <input v-model="formData.package_weight" type="text" id="poids" placeholder="3  Kh"
                            class="w-full border border-gray-300 rounded-full p-2 pr-10 outline-none" />
                          <svg xmlns="http://www.w3.org/2000/svg"
                            class="h-6 w-6 absolute right-3 top-1/2 transform -translate-y-1/2 text-gray-400"
                            viewBox="0 0 20 20" fill="currentColor">
                            <path fill-rule="evenodd" d="M10 12a2 2 0 100-4 2 2 0 000 4z" clip-rule="evenodd" />
                            <path fill-rule="evenodd"
                              d="M4.293 8.293a1 1 0 011.414 0L10 12.586l4.293-4.293a1 1 0 111.414 1.414l-5 5a1 1 0 01-1.414 0l-5-5a1 1 0 010-1.414zM4 5a3 3 0 100 6 3 3 0 000-6z"
                              clip-rule="evenodd" />
                          </svg>
                        </div>
                      </div>
                      <div class="mt-5 grid grid-cols-2 gap-4">
                        <button @click="selectType('Electronique', 'Electronique')"
                          :class="{ 'bg-orange-500 text-white py-2 px-4 rounded-full': selectedType === 'Electronique', 'border border-gray-500 bg-white text-gray-500 py-2 px-4 rounded-full': selectedType !== 'Electronique' }">Electronique</button>
                        <button @click="selectType('Documents', 'Documents')"
                          :class="{ 'bg-orange-500 text-white py-2 px-4 rounded-full': selectedType === 'Documents', 'border border-gray-500 bg-white text-gray-500 py-2 px-4 rounded-full': selectedType !== 'Documents' }">Documents</button>
                      </div>
                    </div>

                    <!-- <button @click="prevStep"
                                    class="bg-white-500 hover:bg-white-700 text-gray font-bold py-2 px-4 rounded-full">
                                    Précédent
                                </button>
                                <button @click="submitForm"
                                    class="float-right bg-green-500 hover:bg-green-700 text-white font-bold py-2 px-4 rounded">
                                    Soumettre
                                </button> -->

                    <button @click="prevStep"
                      class="mt-10 bg-white-500 hover:bg-white-700 text-orange-500 font-bold py-2 px-4 rounded-full border border-orange-500">
                      Précédent
                    </button>

                    <button @click="nextStep"
                      class="float-right mt-10 bg-orange-500 hover:bg-orange-700 text-white font-bold py-2 px-4 rounded-full">
                      Suivant
                    </button>
                  </div>
                  <div v-else-if="step === 4">
                    <!-- 4eme étape du formulaire -->


                    <div class="flex flex-col items-center justify-center">
                      <!-- Boule ronde orange -->
                      <div class="bg-orange-500 rounded-full w-24 h-24 flex items-center justify-center mb-4">
                        <!-- Icône SVG -->
                        <svg class="w-12 h-12 text-white" fill="none" viewBox="0 0 24 24">
                          <!-- Insérez votre icône SVG ici -->
                          <path fill-rule="evenodd"
                            d="M12 22c6.075 0 11-4.925 11-11S18.075 0 12 0 1 4.925 1 11s4.925 11 11 11zm-1.5-8.207V9h3v4.793l-1.146-1.147-1.354 1.353L12 16l2.5-2.5-1.354-1.353-1.146 1.147z"
                            clip-rule="evenodd"></path>
                        </svg>
                      </div>
                      <!-- Texte "Envoie du devis" -->
                      <p class="text-lg font-bold mb-4">Envoie du devis</p>
                      <!-- Texte "Toto" -->
                      <p class="mb-4 text-gray-500">Merci de vous assurer que toutes les
                        information <br>
                        soumises sont
                        correctes. Vous recevrez un devis par <br> Whatsapp, sous 24h et vous
                        pourrez me
                        régler par mobile <br> money / Carte bancaire</p>
                      <!-- Bouton "Envoyer" -->
                      <button class="bg-orange-500 text-white py-2 px-4 rounded-full">Envoyer</button>
                    </div>



                    <!-- <button @click="prevStep"
                                    class="bg-white-500 hover:bg-white-700 text-gray font-bold py-2 px-4 rounded-full">
                                    Précédent
                                </button>
                                <button @click="submitForm"
                                    class="float-right bg-green-500 hover:bg-green-700 text-white font-bold py-2 px-4 rounded">
                                    Soumettre
                                </button> -->

                    <button @click="prevStep"
                      class="mt-6 bg-white-500 hover:bg-white-700 text-orange-500 font-bold py-2 px-4 rounded-full border border-orange-500">
                      Précédent
                    </button>


                  </div>

                </div>


              </form>


            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script >
export default {
  data() {
    return {
      step: 1,
      formData: {
        user_name: '',
        user_email: '',
        user_phone: '',
        transport_mode: '',
        departure_adress: '',
        arrival_adress: '',
        package_value: '',
        package_weight: '',
        package_category: null,
        // selectedType: '',
        
      },
      transport_mode: 'option1',
      // selectedType: 'Electronique' // Sélectionne 'Electronique' par défaut
    };
  },
  methods: {
    nextStep() {
      this.step++;
    },
    prevStep() {
      this.step--;
    },
    async submitForm() {
      this.formData.transport_mode = this.transport_mode;
      console.log('Formulaire soumis :', this.formData);

      try {
        const response = await fetch('https://api-staging.domaloomarket.com/covalisage/', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
            'X-API-KEY': '89c94743-ozel-9596-3air-1b7165824d43' // Ajout de l'en-tête API Key
          },
          body: JSON.stringify(this.formData)
        });

        if (response.ok) {
          console.log('Formulaire soumis avec succès');
          // Réinitialiser le formulaire après soumission réussie si nécessaire
          // this.resetForm();
        } else {
          console.error('Erreur lors de la soumission du formulaire');
        }
      } catch (error) {
        console.error('Une erreur est survenue :', error);
      }
    },

    selectOption(option) {
      this.transport_mode = option;
      this.formData.transport_mode = option; // Ajout de la mise à jour de transport_mode dans formData
      console.log("Option de livraison sélectionnée:", option);
    },

    handleRadioChange(event) {
      this.transport_mode = event.target.value;
    },
    selectTailleColis(tailleColis) {
      this.formData.package_category = tailleColis;
      console.log("Taille de colis sélectionnée :", tailleColis);
    },
    // selectType(type, content) {
    //   this.selectedType = type;
    //   this.formData.selectedType = content; // Ajout du contenu du bouton sélectionné dans formData
    //   console.log("Contenu du bouton cliqué :", content);
    // }
  }
};
</script>


