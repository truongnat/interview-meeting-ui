<template>
  <div class="bottom-action">
    <div class="bottom-action_time">9:57 PM | thg-fbb-dke</div>
    <div class="bottom-action_main-action">
      <v-btn color="error" dark fab small depressed class="mr-3">
        <v-icon light color="#fff" size="20"> mdi-microphone-off </v-icon>
      </v-btn>
      <v-btn color="error" dark fab small depressed class="mr-3">
        <v-icon light color="#fff" size="20"> mdi-camera-off </v-icon>
      </v-btn>
      <v-btn dark fab small depressed class="mr-3">
        <v-icon light color="#fff" size="26">
          mdi-closed-caption-outline
        </v-icon>
      </v-btn>
      <v-btn dark fab small depressed class="mr-3">
        <v-icon light color="#fff" size="26">
          mdi-arrow-up-bold-box-outline
        </v-icon>
      </v-btn>
      <v-btn dark fab small depressed class="mr-3">
        <v-icon light color="#fff" size="26"> mdi-dots-vertical </v-icon>
      </v-btn>
      <v-btn color="error" dark rounded depressed>
        <v-icon light color="#fff" size="26"> mdi-phone-hangup </v-icon>
      </v-btn>
    </div>
    <div class="bottom-action_left-action">
      <v-btn dark fab small depressed class="mr-3">
        <v-icon light color="#fff" size="22"> mdi-information-outline </v-icon>
      </v-btn>
      <v-btn dark fab small depressed class="mr-3">
        <v-icon light color="#fff" size="22">
          mdi-account-cancel-outline
        </v-icon>
      </v-btn>
      <v-btn dark fab small depressed class="mr-3">
        <v-icon light color="#fff" size="22"> mdi-message-text </v-icon>
      </v-btn>
      <v-btn dark fab small depressed class="mr-3">
        <v-icon light color="#fff" size="22"> mdi-shape-outline </v-icon>
      </v-btn>
    </div>
  </div>
</template>
<script>
export default {
  name: 'BottomAction',
};
</script>
<style lang="scss">
.bottom-action {
  height: 80px;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 24px;
  // background: red;

  &_time {
    letter-spacing: 0.00625em;
    font-size: 1rem;
    font-weight: 500;
    line-height: 1.5rem;
    color: #fff;
    max-width: 400px;
    -webkit-user-select: none;
  }
}
</style>
