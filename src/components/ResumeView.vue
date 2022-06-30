<template>
  <div class="card card-w70">
    <template v-if="blocks.length">
      <component
        v-for="block in blocks"
        :key="block.id"
        :is="'resume-' + block.type"
        v-bind="{ value: block.value }"
      ></component>
    </template>
    <h3 v-else>Добавьте первый блок, чтобы увидеть результат</h3>
  </div>
</template>

<script>
import ResumeAvatar from "./parts/ResumeAvatar.vue";
import ResumeTitle from "./parts/ResumeTitle.vue";
import ResumeSubtitle from "./parts/ResumeSubtitle.vue";
import ResumeText from "./parts/ResumeText.vue";

export default {
  props: {
    blocks: Array,
  },
  components: {
    ResumeTitle,
    ResumeAvatar,
    ResumeSubtitle,
    ResumeText,
  },
};
</script>

<style></style>
