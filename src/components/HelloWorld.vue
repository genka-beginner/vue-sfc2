<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button @click="handleClick">カウント {{ count }}</button>
    <CopyDocs docs="For a guide and recipes on how to configure / customize this project," />
    <RefLinks #default="{ links }">
        <div v-for="link in links" :key="link.id">
        <h3>{{ link.title }}</h3>
        <ul>
            <li v-for="li in link.list" :key="li.id">
            <a :href="li.href" target="_blank" rel="noopener">
                {{ li.text }}
            </a>
            </li>
        </ul>
        </div>
    </RefLinks>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import RefLinks from './RefLinks.vue'
import CopyDocs from './CopyDocs.vue'

type Props = {
  msg: string,
  count: number
}

export default defineComponent({
  name: 'HelloWorld',
  components: { RefLinks, CopyDocs },
  props: {
    msg: {
      type: String,
      required: true
    },
    count: {
      type: Number,
      required: true
    }
  },
  emits: ['child-event'],
  setup (props: Props, { emit }) {
    const handleClick = () => {
      emit('child-event', props.count + 1)
    }
    return { handleClick }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button {
  padding: 15px;
  font-size: 1.8rem;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>