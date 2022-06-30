<template>
  <div class="container column">
    <resume-form @block-added="addBlock"></resume-form>
    <resume-view :blocks="blocks"></resume-view>
  </div>
  <div class="container">
    <resume-loader v-if="loading"></resume-loader>
    <resume-comments
      v-else
      @load-comments="loadComments"
      :comments="comments"
    ></resume-comments>
  </div>
</template>

<script>
import ResumeComments from "./components/ResumeComments.vue";
import ResumeForm from "./components/ResumeForm.vue";
import ResumeLoader from "./components/ResumeLoader.vue";
import ResumeView from "./components/ResumeView.vue";
export default {
  data() {
    return {
      blocks: [],
      comments: [],
      loading: false,
    };
  },
  methods: {
    async loadComments() {
      this.loading = true;
      const response = await fetch(
        "https://jsonplaceholder.typicode.com/comments?_limit=42"
      );
      this.comments = await response.json();
      this.loading = false;
    },
    addBlock(block) {
      this.blocks.push(block);
    },
  },
  components: {
    ResumeForm,
    ResumeView,
    ResumeLoader,
    ResumeComments,
  },
};
</script>

<style></style>
