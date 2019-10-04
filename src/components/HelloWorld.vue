<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>{{$attrs.foo}}</p> <!-- 子类可以通过$attrs获取父类传给子类的属性值 -->
    <p>{{xx}}</p>
    <p>{{something}}</p>
    <p><slot></slot></p>
    <p>
      <slot name="content" :xx="xx"></slot> <!-- 分发内容要用到子组件中的数据 -->
    </p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  inject: ['something'],
  props: {
    msg: String
  },
  data() {
    return {
      xx: 'x'
    }
  },
  mounted(){
    this.$on('foo', () => {
      // console.log('foo~~~');
    })

    this.$emit('foo')
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
