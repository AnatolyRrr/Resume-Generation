<template>
  <div class="container column">
    <resume-form></resume-form>
    <resume-view :blocks="blocks"></resume-view>
  </div>
  <div class="container">
    <resume-loader></resume-loader>
    <resume-comments></resume-comments>
  </div>
</template>

<script>
import ResumeComments from './components/ResumeComments.vue'
import ResumeForm from './components/ResumeForm.vue'
import ResumeLoader from './components/ResumeLoader.vue'
import ResumeView from './components/ResumeView.vue'
export default {
  data() {
    return {
      blocks: [],
  },
  components: {
    ResumeForm,
    ResumeView,
    ResumeLoader,
    ResumeComments,
  },
}
</script>

<style>

</style>
