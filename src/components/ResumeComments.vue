<template>
    <div class="card" v-if="comments.length">
      <h2>Комментарии</h2>
      <ul class="list"
        v-for="comment in comments"
        :key="comment.id"
      >
        <li class="list-item">
          <div>
            <p><strong>{{ comment.email }}</strong></p>
            <small>{{ comment.body }}</small>
          </div>
        </li>
        <hr>
      </ul>
    </div>
    <p v-else>
      <button class="btn primary" @click="$emit('load')">Загрузить комментарии</button>
    </p>
</template>

<script>
export default {
  props: ['comments'],
  emits: ['load']
}
</script>