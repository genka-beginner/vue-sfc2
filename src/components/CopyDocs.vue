<template>
<div>
    <p>
      For a guide and recipes on how to configure / customize this project,<br />
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">
      vue-cli documentation
      </a>.
    </p>
</div>
</template>
<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: 'CopyDocs',

  props:{
      docs:{
          type:String,
          requires: true,
      }
  }
});
</script>

<style scoped>
a {
  color: #42b983;
}
</style>