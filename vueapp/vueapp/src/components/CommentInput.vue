<template>
  <div className="commentInput">
    <div className="comment-content">
      <span className="content-name">用户名：</span>
      <div className="content-input">
        <input v-model.trim="username" />
      </div>
    </div>
    <div className="comment-content">
      <span className="content-name">评论内容：</span>
      <div className="content-input">
        <textarea style="width: 306px;height: 198px;" v-model.trim="content" />
      </div>
    </div>
    <div className="content-button">
      <button @click="handleUserInfo">发布</button>
    </div>
  </div>
</template>
<script>
import { ref } from "vue";

export default {
  name: "CommentIput",
  setup(props,{emit}) {
    const username = ref("");
    const content = ref("");
    const handleUserInfo = () => {
      emit("inputinfo", {
        username: username.value,
        content: content.value,
      });
      (username.value = ""), (content.value = "");
    };
    return {
      username,
      content,
      handleUserInfo,
    };
  },
};
</script>
<style>
.commentInput {
  background-color: #fff;
  border: 1px solid rgb(219, 219, 219);
  padding: 20px;
  width: 520px;
  margin: 10px auto;
  font-size: 14px;
}
.comment-content {
  margin-bottom: 15px;
  display: flex;
}
.comment-content .content-name {
  display: flex;
  flex-basis: 100px;
  font-size: 15px;
  color: #1e1e1f;
}
.comment-input .content-input {
  display: flex;
  flex: 1;
  
}

.comment-input input,
.comment-input template {
  border: 1px solid #dad9d9;
  border-radius: 3px;
  padding: 5px;
  outline: none;
  font-size: 14px;
  resize: none;
  flex: 1;
}
.comment-input textarea {
  height: 10px
}
.content-button {
  display: flex;
  justify-content: flex-end;
}
.content-button button {
  padding: 5px 10px;
  width: 80px;
  border: none;
  border-radius: 3px;
  background-color: #80cadf;
  color: #fff;
  outline: none;
  cursor: pointer;
}
.content-button button:hover {
  background: #13c1f1;
}
</style>