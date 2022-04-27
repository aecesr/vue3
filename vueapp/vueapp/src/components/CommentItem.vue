<template>
  <div className="comment">
    <div className="user">
      <span>{{ props.comment.username }} </span>
    </div>
    <p class="content">{{ props.comment.content }}</p>
  </div>
</template>
<script>
import { onMounted } from "vue";
export default {
  name: "CommentItem",
  props: {
    comment: Object,
  },
  setup(props) {
    onMounted(() => {
      console.log(props);
    });
    return {
      props,
    };
  },
};
</script>
<style>
.comment {
  display: flex;
  border-bottom: 1px solid #f1f1f1;
  margin-bottom: 10px;
  padding-bottom: 10px;
  min-height: 55px;
  font-size: 12px;
  font-weight: "宋体";
  line-height: 20px;
}
.comment .content {
  margin: 0;
  margin-left: 20px;
  word-wrap: break-word;
  word-break: break-all;
  min-width: 450px;
  text-align: left;
}
.comment .user {
  flex-shrink: 0;
  font-weight: "宋体";
  font-weight: bold;
  font-size: 12px;
  line-height: 20px;
}
.comment span {
  color: #00a3cf;
  font-style: italic;
}
</style>