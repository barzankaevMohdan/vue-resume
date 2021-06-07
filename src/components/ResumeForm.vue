<template>
    <form
      class="card card-w30"
      @submit.prevent="submit"
      >
      <div class="form-control">
        <label for="type">Тип блока</label>
        <select
          id="type"
          v-model="option"
        >
          <option value="title">Заголовок</option>
          <option value="subtitle">Подзаголовок</option>
          <option value="avatar">Аватар</option>
          <option value="text">Текст</option>
        </select>
      </div>

      <div class="form-control">
        <label for="value">Значение</label>
        <textarea
         id="value"
         rows="3"
         v-model="text"
         ></textarea>
      </div>

      <button
        class="btn primary"
        :disabled="!isValid"
      >Добавить</button>
    </form>
</template>

<script>
export default {
  data() {
    return {
      option: 'title',
      text: ''
    }
  },
  emits: ['add-block'],
  methods: {
    submit() {
      this.$emit('add-block', {
        option: this.option,
        text: this.text,
        id: Date.now()
      })

      this.option = 'title'
      this.text = ''
    }
  },
  computed: {
    isValid() {
      return this.text.length > 3
    }
  }
}
</script>