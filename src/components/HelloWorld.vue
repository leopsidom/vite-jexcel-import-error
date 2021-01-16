<template>
  <div ref="isheet"></div>
</template>

<script lang="ts">
import { ref, defineComponent, onMounted } from "vue";
import jexcel from "jexcel";

export default defineComponent({
  name: "HelloWorld",
  props: {
    msg: {
      type: String,
      required: true,
    },
  },
  setup: () => {
    const isheet = ref<HTMLDivElement | null>(null);
    onMounted(() => {
      if (isheet.value)
        jexcel(isheet.value, {
          minDimensions: [30, 10],
        });
    });
    return { isheet };
  },
});
</script>

<style scoped>
a {
  color: #42b983;
}
</style>