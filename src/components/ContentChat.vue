<template>
  <div class="content-chat">
    <div class="content-chat_author">
      <div class="content-chat_author-name">{{ username }}</div>
      <div class="content-chat_author-time">{{ time }}</div>
    </div>
    <div class="content-chat_messages">
      <div
        class="content-chat_messages-text"
        v-for="(m, idx) in messages"
        :key="`${idx}_${m.text}`"
      >
        {{ m.text }}
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ContentChat',
  props: ['username', 'time', 'messages'],
};
</script>
<style lang="scss" scoped>
.content-chat {
  display: block;
  padding: 14px 24px;

  &_author {
    &-name {
      color: #202124;
      display: inline-block;
      font-size: 13px;
      font-weight: 500;
      line-height: 19px;
      padding-right: 8px;
      word-wrap: break-word;
    }
    &-time {
      color: #5f6368;
      display: inline-block;
      font-size: 12px;
    }
  }

  &_messages {
    display: inline-block;
    max-width: 100%;
    &-text {
      color: #202124;
      font-size: 13px;
      line-height: 20px;
      padding-top: 10px;
      white-space: pre-wrap;
      word-wrap: break-word;
      display: block;
    }
  }
}
</style>
