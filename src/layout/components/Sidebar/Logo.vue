<template>
  <div class="sidebar-logo-container" :class="{'collapse':collapse}">
    <transition name="sidebarLogoFade">
      <router-link v-if="collapse" key="collapse" class="sidebar-logo-link" to="/">
        <!-- <img v-if="logo" :src="logo" class="sidebar-logo"> -->
        <!-- <h1 v-else class="sidebar-title">{{ title }} </h1> -->
        <div class="toggle">
    <div class="avatar-wrapper">
      <div class="user-avatar">
        <img src="@/assets/img/user.jpg" />
      </div>
      <div class="title" v-show="false">
        <span class="one-text">平台管理员</span>
        <span class="two-text">请必填</span>
        <span class="three-text">广东省公安厅</span>
      </div>
    </div>
  </div>

      </router-link>


      <router-link v-else key="expand" class="sidebar-logo-link" to="/">
        <!-- <img v-if="logo" :src="logo" class="sidebar-logo"> -->
        <!-- <h1 class="sidebar-title">{{ title }} </h1> -->
        <div class="toggle">
    <div class="avatar-wrapper">
      <div class="user-avatar">
        <img src="@/assets/img/user.jpg" />
      </div>
      <div class="title">
        <span class="one-text">平台管理员</span>
        <span class="two-text">请必填</span>
        <span class="three-text">广东省公安厅</span>
      </div>
    </div>
  </div>


      </router-link>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'SidebarLogo',
  props: {
    collapse: {
      type: Boolean,
      required: true
    }
  },
  data() {
    return {
      title: 'Vue Element Admin',
      logo: 'https://wpimg.wallstcn.com/69a1c46c-eb1c-4b46-8bd4-e9e686ef5251.png'
    }
  }
}
</script>

<style lang="scss" scoped>
.sidebarLogoFade-enter-active {
  transition: opacity 1.5s;
}

.sidebarLogoFade-enter,
.sidebarLogoFade-leave-to {
  opacity: 0;
}

.sidebar-logo-container {
  position: relative;
  width: 100%;
  // height: 50px;
  // line-height: 50px;
  background: #334376;
  text-align: center;
  // overflow: hidden;

  & .sidebar-logo-link {
    height: 100%;
    width: 100%;

    & .sidebar-logo {
      width: 32px;
      height: 32px;
      vertical-align: middle;
      margin-right: 12px;
    }

    & .sidebar-title {
      display: inline-block;
      margin: 0;
      color: #fff;
      font-weight: 600;
      line-height: 50px;
      font-size: 14px;
      font-family: Avenir, Helvetica Neue, Arial, Helvetica, sans-serif;
      vertical-align: middle;
    }
  }

  &.collapse {
    & .avatar-wrapper{
    display: flex;
    justify-content: center;
    align-items: center;
    transform: scale(0.6);
    flex-direction: column;
    width: 100%;
    transform-origin: left;
    & .user-avatar{
      margin-top: 0;
    }
    }
    .sidebar-logo {
      margin-right: 0px;
    }
  }
}


toggle {
  cursor: pointer;
  position: fixed;
  top: 0;
  left: 0;
  line-height: 1.7rem;
  background: #334376;
  width: 10.5rem;
  height: 11.4rem;
  z-index: 1001;
  // background: rgba(102, 102, 102, 0.192);
  & i {
    font-size: 0.8rem;
    text-align: center;
    line-height: 1.7rem;
    color: white;
  }
  & .is-active {
    transform: rotate(180deg);
  }
}
.avatar-wrapper {
  width: 100%;
  //   height: 100%;
  // border-bottom: 1rem solid #5e97f3;
  & .user-avatar {
    cursor: pointer;
    width: 4.3rem;
    height: 4.3rem;
    border-radius: 50%;
    margin: 0 auto;
    margin-top: 1.6rem;
    & img {
      width: 100%;
      height: 100%;
      border-radius: 50%;
    }
  }
  & .title {
    color: #fff;
    margin-left: 0.75rem;
    margin: 0 auto;
    text-align: center;
    display: flex;
    flex-direction: column;
    padding: .3rem 0;
    & span {
      line-height: 1.4rem;
    }
    & .one-text {
      font-size: 0.9rem;
      font-weight: bold;
    }
    & .two-text {
      font-size: 0.6rem;
    }
    & .three-text {
      font-size: 0.7rem;
      font-weight: bold;
    }
  }
}
</style>
