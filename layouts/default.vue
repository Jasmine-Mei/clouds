<template>
  <div>
    <Header></Header>
    <!-- 内容占位组件 -->
    <!-- 相当于<router-view></router-view> -->
    <nuxt />
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "@/components/header.vue";
import Footer from "@/components/footer.vue";
export default {
  components: {
    Header,
    Footer
  }
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
}
ul,
li,
ol {
  list-style: none;
}
a {
  text-decoration: none;
  color: inherit;
}
a:hover {
  color: inherit;
}
em,
i {
  font-style: normal;
}
</style>
