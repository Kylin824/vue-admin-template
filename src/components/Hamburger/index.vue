<template>
  <!-- 折叠左边菜单栏 -->
  <div style="padding: 0 15px" @click="toggleClick">
    <!-- 直接用svg标签创建一个SVG图案-->
    <svg
      class="hamburger"
      viewBox="0 0 1024 1024"
      xmlns="http://www.w3.org/2000/svg"
      width="64"
      height="64"
      :class="{'is-active':isActive}"
    >
      <!--  如果isActive为true，则添加is-active样式-->
      <path d="M408 442h480c4.4 0 8-3.6 8-8v-56c0-4.4-3.6-8-8-8H408c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8zm-8 204c0 4.4 3.6 8 8 8h480c4.4 0 8-3.6 8-8v-56c0-4.4-3.6-8-8-8H408c-4.4 0-8 3.6-8 8v56zm504-486H120c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h784c4.4 0 8-3.6 8-8v-56c0-4.4-3.6-8-8-8zm0 632H120c-4.4 0-8 3.6-8 8v56c0 4.4 3.6 8 8 8h784c4.4 0 8-3.6 8-8v-56c0-4.4-3.6-8-8-8zM142.4 642.1L298.7 519a8.84 8.84 0 0 0 0-13.9L142.4 381.9c-5.8-4.6-14.4-.5-14.4 6.9v246.3a8.9 8.9 0 0 0 14.4 7z" />
    </svg>
  </div>
</template>

<script>
export default {
  name: 'Hamburger',
  props: {
    // 接受NavBar组件传过来的is-active的值
    isActive: {
      type: Boolean, // 限制类型
      default: false // 默认值
    }
  },
  methods: {
    toggleClick() {
      // 点击时触发，回调Navbar中的toggleClick事件
      this.$emit('toggleClick')
    }
  }
}
</script>

<style scoped>
.hamburger {
  /* ? */
  display: inline-block;
  /*图像居中*/
  vertical-align: middle;
  width: 20px;
  height: 20px;
}

.hamburger.is-active {
  /*图像元素旋转180度*/
  transform: rotate(180deg);
}
</style>
