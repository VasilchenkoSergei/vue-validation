<template>
  <div class="user-form">
    <form action="">
      <div class="form-field">
        <input type="text" placeholder="Имя" class="form-field__input">
      </div>
      <div class="form-field">
        <input type="text" placeholder="Фамилия" class="form-field__input">
      </div>
      <div class="form-field">
        <input type="checkbox" id="checkbox1" class="form-field__checkbox">
        <label for="checkbox1">Правила пользования</label>
      </div>
      <div class="form-field">
        <input type="checkbox" id="checkbox2" class="form-field__checkbox">
        <label for="checkbox2">Условия соглашения</label>
      </div>
      <div class="form-field">
        <input type="radio" name="radioButtons" id="radio1" class="form-field__radio">
        <label for="radio1">Условие 1</label>
        <input type="radio" name="radioButtons" id="radio2" class="form-field__radio">
        <label for="radio2">Условие 2</label>
        <input type="radio" name="radioButtons" id="radio3" class="form-field__radio">
        <label for="radio3">Условие 3</label>
        <input type="radio" name="radioButtons" id="radio4" class="form-field__radio">
        <label for="radio4">Условие 4</label>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {

    }
  },
  methods: {

  }
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
  }
</style>