<!--component-1
<template>
  <MyBtn>Banana</MyBtn>
  <MyBtn
    :color="color">
    <span style="color: red;">Banana</span>
  </MyBtn>
  <MyBtn
    large
    color="Orange">
    Apple
  </MyBtn>
  <MyBtn
    large
    color="royalblue">
    Grape
  </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default {
  components: {
    MyBtn
  },
  data() {
    return {
      color: '#000'
    }
  }
}
</script>-->

<!--속성 상속-->
<template>
  <MyBtn
    class="heropy"
    style="color: red;"
    title="Hello world!">
    Banana
  </MyBtn>
  <MyBtn class="jb">
    apple
  </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default {
  components: {
    MyBtn
  }
}
</script>
