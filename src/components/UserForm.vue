<template>
  <div class="user-form">
    <form action="" @submit.prevent="submitForm">
      <div class="form-field" :class="$v.userName.$error ? 'error' : ''">
        <input id="userName" type="text" placeholder="Имя"
          class="form-field__input" v-model.trim="$v.userName.$model"
        >
        <span v-if="$v.userName.$dirty && !$v.userName.required">введите что-нибудь</span>
        <span v-if="$v.userName.$dirty && !$v.userName.minLength">минимальное количество</span>
      </div>
      <div class="form-field">
        <input id="userSurname" type="text" placeholder="Фамилия" class="form-field__input" v-model.trim="userSurname">
      </div>
      <div class="form-field">
        <input id="userFathername" type="text" placeholder="Отчество" class="form-field__input" v-model.trim="userFathername">
      </div>
      <div class="form-field">
        <input id="useEmail" type="text" placeholder="Email" class="form-field__input" v-model.trim="userEmail">
      </div>
      <div class="form-field">
        <input type="checkbox" id="checkbox1" class="form-field__checkbox" v-model="useRules">
        <label for="checkbox1">Правила пользования</label>
      </div>
      <div class="form-field">
        <input type="checkbox" id="checkbox2" class="form-field__checkbox" v-model="useConditions">
        <label for="checkbox2">Условия соглашения</label>
      </div>
      <div class="form-field">
        <input type="radio" name="radioButtons" id="radio1" class="form-field__radio" v-model="condition">
        <label for="radio1">Условие 1</label>
        <input type="radio" name="radioButtons" id="radio2" class="form-field__radio" v-model="condition">
        <label for="radio2">Условие 2</label>
        <input type="radio" name="radioButtons" id="radio3" class="form-field__radio" v-model="condition">
        <label for="radio3">Условие 3</label>
        <input type="radio" name="radioButtons" id="radio4" class="form-field__radio" v-model="condition">
        <label for="radio4">Условие 4</label>
      </div>
      <div class="form-field">
        <select class="form-field__select">
          <option :value="option.value" v-for="(option, index) in selectOptions" :key="option.value + index">{{ option.title }}</option>
        </select>
      </div>
      <button class="form-button">Зарегестрировать</button>
    </form>
  </div>
</template>

<script>
import { validationMixin } from 'vuelidate';
const { required, minLength } = require('vuelidate/lib/validators');

export default {
  mixins: [validationMixin],
  data() {
    return {
      userName: '',
      userSurname: '',
      userFathername: '',
      userEmail: '',
      useRules: '',
      useConditions: '',
      condition: '',
      selectOptions: [
        {
          value: 'vibor 1',
          title: 'Выбор 1',
        },
        {
          value: 'vibor 2',
          title: 'Выбор 2',
        },
        {
          value: 'vibor 3',
          title: 'Выбор 3',
        },
      ]
    }
  },
  validations: {
    userName: {
      required,
      minLength: minLength(5),
    }
  },
  methods: {
    submitForm() {
      this.$v.$touch();

      if (this.$v.$error) {
        console.log('Успех!');
      }
    },
  },
}
</script>

<style lang="scss" scoped>
  .user-form  {
    padding-top: 100px;
    padding-left: 100px;
    
  }

  .form-field {
    margin-bottom: 30px;


    &__input {
      height: 40px;
      width: 500px;
      line-height: 40px;
      padding-left: 20px;
      font-size: 20px;
    }

    &__select {
      width: 500px;
      height: 40px;
    }

    &.error {
      border: 1px solid red;
    }
  }

  .form-button {
    height: 50px;
    width: 500px;
    font-size: 20px;
  }
</style>