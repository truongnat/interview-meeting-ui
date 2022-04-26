<template>
  <v-app>
    <!-- top -->
    <div class="layout-top">
      <!-- layout tile -->
      <div class="layout-top-tile">
        <TileView :isBordering="true" :isShowCamera="true" />
        <TileView
          :username="'truong 2001'"
          :isAvatar="true"
          :avatar="'https://taimienphi.vn/tmp/cf/aut/hinh-anh-canh-dep-viet-nam-1.jpg'"
        />
        <TileView :username="'You'" />
      </div>
      <!-- layout chat -->
      <div class="layout-top-chat">
        <LayoutChat />
      </div>
    </div>
    <!-- bottom -->
    <BottomAction />
  </v-app>
</template>

<script>
import TileView from './components/TileView.vue';
import LayoutChat from './components/LayoutChat.vue';
import BottomAction from './components/BottomAction.vue';
export default {
  name: 'App',

  components: { TileView, LayoutChat, BottomAction },

  data: () => ({
    //
  }),
};
</script>

<style scoped lang="scss">
#app {
  background-color: #282424;
  font-family: 'Roboto', sans-serif;
  margin: 0;
  padding: 0;
}

.layout-top {
  display: flex;
  align-items: center;
  padding: 12px 12px 0 24px;
  position: relative;
  height: calc(100vh - 80px);

  &-chat {
    width: 360px;
    height: 100%;
  }

  &-tile {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    width: calc(100% - 360px);
  }
}
</style>
