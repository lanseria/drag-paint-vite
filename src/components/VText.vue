<template>
  <div class="v-n-text" :style="{ ...sizeStyle }">文字</div>
</template>
<script lang="ts">
import { defineComponent, ref, PropType, computed } from "vue";
import { NInput } from "naive-ui";
import { useSizeStyle } from "../hooks/style";
export default defineComponent({
  name: "VText",
  props: {
    item: {
      type: Object as PropType<ComponentItem>,
      required: true,
    },
  },
  components: {
    NInput,
  },
  setup(props) {
    const { sizeStyle } = useSizeStyle(props);
    const value = ref("");
    return {
      value,
      sizeStyle,
    };
  },
});
</script>
<style lang="css" scoped>
.v-n-text {
  display: flex;
  border: 1px dashed #000;
}
</style>
