<template>
  <div id="app">
    <div class="container">
      <section class="page-section">
        <div class="page-section__wrapper">
          <h1 class="title">Создание клиента</h1>
          <InputComponent
            :inputSub="`Поле обязательно для заполнения`"
            :placeholder="`Фамилия`"
          />
          <InputComponent
            :inputSub="`Поле обязательно для заполнения`"
            :placeholder="`Имя`"
          />
          <InputComponent
            :inputSub="`Поле обязательно для заполнения`"
            :placeholder="`Отчество`"
          />
        </div>
      </section>
    </div>
    <router-view />
  </div>
</template>

<script>
import InputComponent from "./components/inputContent";
export default {
  components: {
    InputComponent,
  },
};
</script>

<style lang="scss">
#app {
  color: #292f40;
}
</style>
