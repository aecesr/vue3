<template>
  <CommentInput @inputinfo="receiveInfo" />
  <CommentList :custom ="Comments" />
</template>

<script>
import CommentInput from "./CommentInput.vue";
import CommentList from "./CommentList.vue";
import { ref } from "vue";

export default {
  name: "CommentApp",
  components: {
    CommentInput,
    CommentList,
  },
  setup() {
    const customcomment = ref({});
    const Comments = ref([]);
    const receiveInfo = (e) => {
      Comments.value.push(e);
      console.log(Comments.value);
    };
    return {
      customcomment,
      receiveInfo,
      Comments,
    };
  },
};
</script>
