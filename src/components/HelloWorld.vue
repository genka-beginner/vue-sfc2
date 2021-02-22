<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button @click="handleClick">カウント{{ count }}</button>
    <!-- <button @click="handleClick2">減算{{ count }}</button> -->
    <CopyDocs />
    <RefLinks />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import RefLinks from "./RefLinks.vue";
import CopyDocs from "./CopyDocs.vue";

type Props = {
  msg: string;
  count: number;
};
export default defineComponent({
  name: "HelloWorld",
  components: {
    RefLinks,
    CopyDocs,
  },
  props: {
    msg: {
      type: String,
      required: true,
    },
    count: {
      type: Number,
      required: true,
    },
  },
  //   emits: ["child-event"],
  setup(props: Props, { emit }) {
    const handleClick = () => {
      emit("child-event", props.count + 1);
    };
    // const handleClick2 = () => {
    //   emit("child-event2", props.count - 1);
    // };
    return { handleClick };

  },
});
</script>

<style>
button {
  padding: 15px;
  font-size: 1.8rem;
}
</style>
