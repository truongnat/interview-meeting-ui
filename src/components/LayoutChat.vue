<template>
  <div class="layout-chat">
    <div class="layout-chat_header">
      <div class="layout-chat_header-text">In-call messages</div>
      <v-btn light icon large>
        <v-icon dark> mdi-close </v-icon>
      </v-btn>
    </div>
    <div class="layout-chat_body">
      <div class="layout-chat_body-box-message">
        Messages can only be seen by people in the call and are deleted when the
        call ends.
      </div>
      <ContentChat
        v-for="item in mockData"
        :key="item.id"
        :username="item.username"
        :time="item.time"
        :messages="item.messages"
      />
    </div>
    <div class="layout-chat_footer">
      <v-textarea
        class="layout-chat_footer-input"
        placeholder="Send a message to everyone"
        filled
        rounded
        dense
        type="text"
        rows="1"
        no-resize
        hide-details
        @change="(val) => (value = val)"
      >
        <template v-slot:append>
          <v-btn icon class="layout-chat_footer-input_icon" large>
            <v-icon dark :color="iconSendColor"> mdi-send-outline </v-icon>
          </v-btn>
        </template>
      </v-textarea>
    </div>
  </div>
</template>
<script>
import ContentChat from './ContentChat.vue';
export default {
  name: 'LayoutChat',
  components: { ContentChat },
  data() {
    return {
      value: '',
      iconSendColor: '#a8a8a8',
      mockData: [
        {
          id: Date.now(),
          username: 'truong 2001',
          time: '12:26 AM',
          messages: [
            {
              text: 'demo ui google meeting',
            },
            {
              text: 'demo not responsive, only device laptop 15.6 inch',
            },
          ],
        },
      ],
    };
  },
  watch: {
    value(newVal) {
      if (newVal !== '') {
        this.iconSendColor = '#1e73e8';
      } else {
        this.iconSendColor = '#a8a8a8';
      }
    },
  },
};
</script>
<style lang="scss">
.layout-chat {
  width: 100%;
  height: 100%;
  background-color: #fff;
  border-radius: 8px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  &_header {
    display: flex;
    align-items: center;
    padding: 0 0 0 24px;
    height: 64px;
    min-height: 64px;
    &-text {
      color: #000;
      font-size: 1.125rem;
      font-weight: 400;
      letter-spacing: 0;
      line-height: 1.5rem;
      box-flex: 1;
      flex-grow: 1;
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
    }
  }

  &_body {
    padding: 12px;
    flex: 1;
    &-box-message {
      letter-spacing: 0.025em;
      font-family: Roboto, Arial, sans-serif;
      font-size: 0.75rem;
      font-weight: 400;
      line-height: 1rem;
      background: #f1f3f4;
      border-radius: 8px;
      margin: 12px;
      text-align: center;
      padding: 12px;
      -webkit-user-select: none;
    }
  }
  &_footer {
    padding: 16px;

    &-input {
      height: 40px;

      & .v-input__slot {
        padding-right: 0px !important;
      }

      & .v-text-field__slot {
        font-size: 13px;
      }

      & .v-input__append-inner {
        margin: 0 !important;
      }
    }
  }
}
</style>
