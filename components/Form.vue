<template>
  <div class="flex items-center justify-center min-w-full h-screen bg-gray-300 p-6">
    <form class="w-full max-w-lg" @submit.prevent="submitForm">
      <div class="flex flex-wrap mb-3">
        <div class="w-full md:w-1/3 px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="last-name">
            Фамилия
          </label>
          <input 
            @input="validateInput"
            v-model="lastName"
            class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" 
            id="last-name" 
            type="text" 
            placeholder="Фамилия" 
            required
          >
        </div>
        <div class="w-full md:w-1/3 px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="first-name">
            Имя
          </label>
          <input 
            @input="validateInput"
            v-model="firstName"
            class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" 
            id="first-name" 
            type="text" 
            placeholder="Имя" 
            required
          >
        </div>
        <div class="w-full md:w-1/3 px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="patronymic">
            Отчество
          </label>
          <input 
            @input="validateInput"
            v-model="patronymic"
            class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" 
            id="patronymic" 
            type="text" 
            placeholder="Отчество"
          >
        </div>
      </div>
      <div class="flex flex-wrap mb-3">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="phone-number">
            Номер телефона
          </label>
          <input 
            @input="prependCountryCode"
            v-model="phoneNumber"
            class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" 
            id="phone-number" 
            type="tel" 
            placeholder="+7 (XXX) XXX-XX-XX" 
            required
          >
        </div>
      </div>
      <div class="flex flex-wrap mb-3">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-email">
            Email
          </label>
          <input 
            v-model="email"
            class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" 
            id="grid-email" 
            type="email" 
            placeholder="example@gmail.com"
          >
        </div>
      </div>
      <div class="flex flex-wrap mb-3">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-password">
            Password
          </label>
          <input 
            v-model="password"
            class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" 
            id="grid-password" 
            type="password" 
            placeholder="******************"
          >
        </div>
      </div>
      <div class="flex flex-wrap mb-3">
        <div class="w-full px-3">
          <button type="submit" class="w-full bg-blue-500 text-white font-bold rounded py-3 px-4 mb-3 leading-tight">
            Отправить
          </button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lastName: '',
      firstName: '',
      patronymic: '',
      phoneNumber: '',
      email: '',
    };
  },
  methods: {
    validateInput() {
      this.lastName = this.lastName.replace(/[^А-ЯЁа-яё\s]/g, '');
      this.firstName = this.firstName.replace(/[^А-ЯЁа-яё\s]/g, '');
      this.patronymic = this.patronymic.replace(/[^А-ЯЁа-яё\s]/g, '');
    },
    prependCountryCode() {
      if (!this.phoneNumber.startsWith('+7')) {
        this.phoneNumber = '+7' + this.phoneNumber;
      }
    },
    submitForm() {
      alert('Данные отправлены: ' + JSON.stringify({
        lastName: this.lastName,
        firstName: this.firstName,
        patronymic: this.patronymic,
        phoneNumber: this.phoneNumber,
        email: this.email,
      }));
      this.lastName = '';
      this.firstName = '';
      this.patronymic = '';
      this.phoneNumber = '';
      this.email = '';
      this.password = '';
    }
  }
};
</script>

<style>

</style>
