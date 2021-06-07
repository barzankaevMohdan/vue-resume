<template>
  <div class="container column">
    <resume-form
      @add-block="addBlock"
    >
    </resume-form>
    <resume-view
    :blocks="this.blocks"
    >
    </resume-view>
  </div>
  <div class="container">
    <resume-comments
      @load="commetnsLoad"
      v-if="!loading"
      :comments="this.comments"
    >
    </resume-comments>
    <app-loader v-if="loading"></app-loader>
  </div>
</template>

<script>
import ResumeForm from './components/ResumeForm'
import ResumeComments from './components/ResumeComments'
import ResumeView from './components/ResumeView'

import AppLoader from './components/AppLoader'

export default {
  data() {
    return {
      blocks: [],
      comments: [],
      loading: false
    }
  },
  methods: {
    addBlock(block) {
      this.blocks.push(block)
    },
    async commetnsLoad() {
      this.loading = true
      const response = await fetch('https://jsonplaceholder.typicode.com/comments?_limit=42')
      this.comments = await response.json()
      this.loading = false
    }
  },
  components: { ResumeForm, ResumeComments, ResumeView, AppLoader }
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
