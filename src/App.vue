<script setup>
import { ref } from 'vue'

const clientInfo = ref({
  name: '',
  email: '',
  password: '',
  passwordConfirm: '',
  confirm: '',
  date: 0,
  address: '',
  city: '',
  state: '',
  confirmState: '',
  hobbies: '',
  programmingLanguage: '',
  biography: ''
});

const showpassword = ref(false);

const states = [
  { acronym: 'AC', namestate: 'Acre' },
  { acronym: 'AL', namestate: 'Alagoas' },
  { acronym: 'AP', namestate: 'Amapá' },
  { acronym: 'AM', namestate: 'Amazonas' },
  { acronym: 'BA', namestate: 'Bahia' },
  { acronym: 'CE', namestate: 'Ceará' },
  { acronym: 'DF', namestate: 'Distrito Federal' },
  { acronym: 'ES', namestate: 'Espírito Santo' },
  { acronym: 'GO', namestate: 'Goiás' },
  { acronym: 'MA', namestate: 'Maranhão' },
  { acronym: 'MT', namestate: 'Mato Grosso' },
  { acronym: 'MS', namestate: 'Mato Grosso do Sul' },
  { acronym: 'MG', namestate: 'Minas Gerais' },
  { acronym: 'PA', namestate: 'Pará' },
  { acronym: 'PB', namestate: 'Paraíba' },
  { acronym: 'PR', namestate: 'Paraná' },
  { acronym: 'PE', namestate: 'Pernambuco' },
  { acronym: 'PI', namestate: 'Piauí' },
  { acronym: 'RJ', namestate: 'Rio de Janeiro' },
  { acronym: 'RN', namestate: 'Rio Grande do Norte' },
  { acronym: 'RS', namestate: 'Rio Grande do Sul' },
  { acronym: 'RO', namestate: 'Rondônia' },
  { acronym: 'RR', namestate: 'Roraima' },
  { acronym: 'SC', namestate: 'Santa Catarina' },
  { acronym: 'SP', namestate: 'São Paulo' },
  { acronym: 'SE', namestate: 'Sergipe' },
  { acronym: 'TO', namestate: 'Tocantins' }
];
</script>

<template>
 <div>
    <form>
      <div class="card text-bg-secondary mb-5 mt-5">
        <div class="card-header text-bg-primary text-center">
          <h1>Form</h1>
        </div>
        <div class="card-body">
          <h2 class="card-title">Enter the information:</h2>

          <div class="form-group">
            <label for="clientInfo.name">Name:</label>
            <input
              type="text"
              v-model="clientInfo.name"
              class="form-control"
              placeholder="Name"
              required
            />
          </div>

          <div class="form-group">
            <label for="clientInfo.email">E-mail:</label>
            <input
              type="email"
              v-model="clientInfo.email"
              class="form-control"
              placeholder="E-mail"
              required
            />
          </div>

          <div class="form-group">
            <label for="clientInfo.password" class="form-label">password</label>
            <div class="input-group">
              <input
                class="form-control"
                v-model="clientInfo.password"
                :type="showpassword ? 'text' : 'password'"
              />
              <button
                class="btn btn-light"
                type="button"
                @click="showpassword = !showpassword"
              >
                Mostrar
              </button>
            </div>
          </div>

          <div class="form-group">
            <label for="passwordConfirm" class="form-label">Confirm the password</label>
            <div class="input-group">
              <input
                class="form-control"
                v-model="clientInfo.passwordConfirm"
                :type="showpassword ? 'text' : 'password'"
              />
            </div>
          </div>

          <div class="form-group">
            <label for="clientInfo.dateBirth">Date of Birth:</label>
            <input
              type="date"
              v-model="clientInfo.dateBirth"
              class="form-control"
              placeholder="Date of Birth"
              required
            />
          </div>
          
          <div>
            <div class="form-group">
              <label for="clientInfo.confirmstate">State:</label>
              <select v-model="clientInfo.confirmstate" class="form-control" required>
                
                <option value="" disabled>Select the state</option>
                <option v-for="state in states" :key="state.acronym" :value="state.namestate">
                  {{ state.acronym }} - {{ state.namestate }}
                </option>
              </select>
            </div>


          <div class="form-group">
            <label for="clientInfo.city">City:</label>
            <input
              type="text"
              v-model="clientInfo.city"
              class="form-control"
              placeholder="City"
              required
            />
          </div>

          <div class="form-group">
            <label for="clientInfo.address">Address:</label>
            <input
              type="text"
              v-model="clientInfo.address"
              name="address"
              class="form-control"
              placeholder="Address"
              required
            />
          </div>

            <div class="form-group">
              <label for="clientInfo.hobbies">Hobbies:</label>
              <input
                type="text"
                v-model="clientInfo.hobbies"
                name="Hobbies"
                class="form-control"
                placeholder="Hobbies"
                required
              />
            </div>
            <div class="form-group">
              <label for="clientInfo.programmingLanguage">Programming Languages:</label>
              <input
                type="text"
                v-model="clientInfo.programmingLanguage"
                name="Programming Languages"
                class="form-control"
                placeholder="Programming Languages"
                required
              />
            </div>
            <div class="form-group">
              <label for="clientInfo.biography">Biography:</label>
              <input
                type="text"
                v-model="clientInfo.biography"
                name="Biography"
                class="form-control"
                placeholder="Biography"
                required
              />
            </div>
            </div>
          </div>
        </div>
    </form>
  </div>
</template>

<style scoped>
</style>
