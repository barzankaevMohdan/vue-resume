<template>
  <div class="card card-w70">
    <template v-if="blocks.length">
      <component
        v-for="block in blocks"
        :key="block.id"
        :is="'resume-' + block.option"
        v-bind="{text: block.text}"
      ></component>
    </template>
    <h3 v-else>Добавьте первый блок, чтобы увидеть результат</h3>
  </div>
</template>

<script>
import ResumeAvatar from './resume/ResumeAvatar'
import ResumeSubtitle from './resume/ResumeSubtitle'
import ResumeText from './resume/ResumeText'
import ResumeTitle from './resume/ResumeTitle'

export default {
  props: ['blocks'],
  components: {
    ResumeTitle,
    ResumeText,
    ResumeSubtitle,
    ResumeAvatar
  }
}
</script>