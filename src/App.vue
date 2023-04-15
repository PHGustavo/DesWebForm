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
})

function sendForm() {
  sentInfo.value = {
    name: clientInfo.value.name,
    email: clientInfo.value.email,
    password: clientInfo.value.password,
    passwordConfirm: clientInfo.value.passwordConfirm,
    dateBirth: clientInfo.value.dateBirth,
    address: clientInfo.value.address,
    city: clientInfo.value.city,
    state: clientInfo.value.confirmState,
    hobbies: clientInfo.value.hobbies,
    programmingLanguage: clientInfo.value.programmingLanguage,
    biography: clientInfo.value.biography
  }
}

const showForm = ref(true)
const showPassword = ref(false)
const sentInfo = ref(null)

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
]
</script>

<template>
  <div v-if="(showForm = !sentInfo)">
    <form @submit.prevent="sendForm">
      <div class="card text-bg-secondary mb-5 mt-5">
        <div class="card-header text-bg-primary text-center">
          <h1>Form</h1>
        </div>
        <div class="card-body">
          <h2 class="card-title">Enter the information:</h2>

          <div class="form-group">
            <label for="clientInfo.name">Name:</label>
            <input type="text" v-model="clientInfo.name" class="form-control" required />
          </div>

          <div class="form-group">
            <label for="clientInfo.email">E-mail:</label>
            <input type="email" v-model="clientInfo.email" class="form-control" required />
          </div>

          <div class="form-group">
            <label for="clientInfo.password" class="form-label">Password</label>
            <div class="input-group">
              <input
                class="form-control"
                v-model="clientInfo.password"
                :type="showPassword ? 'text' : 'password'"
              />
              <button class="btn btn-light" type="button" @click="showPassword = !showPassword">
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
                :type="showPassword ? 'text' : 'password'"
              />
            </div>
          </div>

          <div class="form-group">
            <label for="clientInfo.dateBirth">Date of Birth:</label>
            <input type="date" v-model="clientInfo.dateBirth" class="form-control" required />
          </div>

          <div>
            <div class="form-group">
              <label for="clientInfo.confirmState">State:</label>
              <select v-model="clientInfo.confirmState" class="form-control" required>
                <option v-for="state in states" :key="state.acronym" :value="state.namestate">
                  {{ state.namestate }}
                </option>
              </select>
            </div>

            <div class="form-group">
              <label for="clientInfo.city">City:</label>
              <input type="text" v-model="clientInfo.city" class="form-control" required />
            </div>

            <div class="form-group">
              <label for="clientInfo.address">Address:</label>
              <input
                type="text"
                v-model="clientInfo.address"
                name="address"
                class="form-control"
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
                required
              />
            </div>
            <div class="d-grid gap-2 mt-3">
              <button class="btn btn-info" type="submit">Send</button>
            </div>
          </div>
        </div>
      </div>
    </form>
  </div>

  <div v-if="sentInfo">
    <div class="card text-bg-secondary" >
      <div class="card-header text-bg-warning text-center">
        <h1>Form</h1>
      </div>
      <div class="card-body">
        <h2 class="card-title">Your Info:</h2>
        <div>
          <ul class="list-group list-group-flush">
            <label for="itemName">Name:</label>
            <div>
              <div class="form-control">
                <li class="list-group-item">{{ sentInfo.name }}</li>
              </div>
            </div>

            <label for="itemName">Email:</label>
            <div>
              <div class="form-control">
                <li class="list-group-item">{{ sentInfo.email }}</li>
              </div>
            </div>

            <label for="itemName">Password:</label>
            <div>
              <div class="form-control">
                <li class="list-group-item">{{ sentInfo.password }}</li>
              </div>
            </div>
            <label for="itemName">Confirm:</label>
            <div>
              <div class="form-control">
                <li class="list-group-item">{{ sentInfo.passwordConfirm }}</li>
              </div>
            </div>
            <label for="itemName">Date of Birth:</label>
            <div>
              <div class="form-control">
                <li class="list-group-item">{{ sentInfo.dateBirth }}</li>
              </div>
            </div>

            <label for="itemName">State:</label>
            <div class="form-control">
              <div>
                <li class="list-group-item">{{ sentInfo.state }}</li>
              </div>
            </div>

            <label for="itemName">City:</label>
            <div>
              <div class="form-control">
                <li class="list-group-item">{{ sentInfo.city }}</li>
              </div>
            </div>

            <label for="itemName">Address:</label>
            <div>
              <div class="form-control">
                <li class="list-group-item">{{ sentInfo.address }}</li>
              </div>
            </div>

            <label for="itemName">Hobbies:</label>
            <div>
              <div class="form-control">
                <li class="list-group-item">{{ sentInfo.hobbies }}</li>
              </div>
            </div>
            <label for="itemName">Programming Languages:</label>
            <div>
              <div class="form-control">
                <li class="list-group-item">{{ sentInfo.programmingLanguage }}</li>
              </div>
            </div>
            <label for="itemName">Biography:</label>
            <div>
              <div class="form-control">
                <li class="list-group-item">{{ sentInfo.biography }}</li>
              </div>
            </div>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
