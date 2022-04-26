<template>
  <div class="tile-view">
    <div class="tile-view-bordering" v-if="isBordering"></div>
    <img
      v-if="isShowCamera"
      src="https://image-us.24h.com.vn/upload/2-2020/images/2020-05-19/1589824016-305c6dbcc81e6bee4378082c46571536.jpg"
      alt="fake-image"
      class="tile-view_fake-image"
    />
    <div v-else class="tile-view_fallback-image">
      <div>
        <img v-if="isAvatar" :src="avatar" alt="fake-image" />
        <span v-else> A</span>
      </div>
    </div>
    <div class="tile-view_name">{{ username || 'Phương Anh Nguyễn' }}</div>
    <div class="tile-view_action">
      <v-icon color="blue" light size="26"> mdi-dots-horizontal-circle </v-icon>
    </div>
  </div>
</template>
<script>
export default {
  name: 'TileView',
  props: ['isBordering', 'isShowCamera', 'username', 'isAvatar', 'avatar'],
};
</script>
<style lang="scss">
.tile-view {
  width: 538px;
  height: 300px;
  position: relative;
  background-color: rgba(54, 55, 58, 255);
  border-radius: 8px;
  overflow: hidden;
  margin: 8px;

  &-bordering {
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 8px;
    border: 4px solid #669df6;
  }

  &_fake-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  &_fallback-image {
    position: absolute;
    offset: 0;
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;

    & > div {
      width: 160px;
      height: 160px;
      background-color: rgb(182, 106, 35);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      & > span {
        font-size: 50px;
        font-weight: 600;
        color: white;
      }

      & > img {
        width: 100%;
        height: 100%;
        border-radius: 50%;
        object-fit: cover;
      }
    }

    &_show-avatar {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }

  &_name {
    position: absolute;
    bottom: 15px;
    left: 10px;
    font-size: 0.875rem;
    font-weight: 500;
    line-height: 1.25rem;
    color: #fff;
    letter-spacing: 0.2px;
    overflow: hidden;
    text-overflow: ellipsis;
    text-shadow: 0 1px 2px rgb(0 0 0 / 60%), 0 0 2px rgb(0 0 0 / 30%);
    white-space: nowrap;
  }

  &_action {
    position: absolute;
    top: 5px;
    right: 5px;
  }
}
</style>
