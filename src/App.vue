<template>
  <div class="container column">
    <form class="card card-w30"
      @submit="submitHandler"
    >
      <div class="form-control">
        <label for="type">Тип блока</label>
        <select id="type">
          <option value="title">Заголовок</option>
          <option value="subtitle">Подзаголовок</option>
          <option value="avatar">Аватар</option>
          <option value="text">Текст</option>
        </select>
      </div>

      <div class="form-control">
        <label for="value">Значение</label>
        <textarea id="value" rows="3"></textarea>
      </div>

      <button class="btn primary">Добавить</button>
    </form>
    <div class="card card-w70">
      <app-resume></app-resume>
      <app-avatar></app-avatar>
      <app-experience></app-experience>
      <app-descr></app-descr>
      <app-title></app-title>
    </div>
  </div>
  <div class="container">
    <p>
      <button class="btn primary">Загрузить комментарии</button>
    </p>
    <div class="card">
      <h2>Комментарии</h2>
      <ul class="list">
        <li class="list-item">
          <div>
            <p><strong>test@microsoft.com</strong></p>
            <small>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi, reiciendis.</small>
          </div>
        </li>
      </ul>
    </div>
    <div class="loader"></div>
  </div>
</template>

<script>

import AppResume from './components/AppResume'
import AppAvatar from './components/AppAvatar'
import AppExperience from './components/AppExperience'
import AppDescr from './components/AppDescr'
import AppTitle from './components/AppTitle'

export default {
  components: { AppResume, AppAvatar, AppExperience, AppDescr, AppTitle }
}
</script>

<style>
  .avatar {
    display: flex;
    justify-content: center;
  }

  .avatar img {
    width: 150px;
    height: auto;
    border-radius: 50%;
  }
</style>
