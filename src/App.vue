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

<!--속성 상속
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
</script>-->

<!--Emit
<template>
  <MyBtn
    @heropy="log"
    @change-msg="logMsg">
    Banana
  </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'
export default {
  components: {
    MyBtn
  },
  methods: {
    log(event) {
      console.log('Click!!')
      console.log(event)
    },
    logMsg(msg) {
      console.log(msg)
    }
  }
}
</script>-->

<!--slot

<template>
  <MyBtn>
    <template #text>
      <span>Banana</span>
    </template>
    <template #icon>
      <span>(B)</span>
    </template>
  </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default {
  components: {
    MyBtn
  }
}
</script>-->

<!--Provide & inject-1

<template>
  <Parent :msg="message" />
</template>

<script>
import Parent from '~/components/Parent'

export default {
  components: {
    Parent
  },
  data() {
    return {
      message: 'Hello world!'
    }
  }
}
</script>-->

<!--Provide & inject-2

<template>
  <button @click="message = 'Good?'">
    Click!
  </button>
  <h1>App: {{ message }}</h1>
  <Parent />
</template>

<script>
import Parent from '~/components/Parent'
import { computed } from 'vue'
export default {
  components: {
    Parent
  },
  data() {
    return {
      message: 'Hello world!'
    }
  },

  provide() {
    return {
      // msg: this.message
      msg: computed(() => this.message) // provide 자체는 반응성이 아니므로 computed를 가지고 와서 반응성을 유지 할 수 있게 만들어줌
    }
  }
}
</script>-->

<!--Refs-1

<template>
  <h1 ref="hello">
    Hello world!
  </h1>
</template>

<script>
export default {
  created() {
    console.log(this.$refs.hello)
  },
  mounted() {
    // const h1El = document.querySelector('#hello')
    console.log(this.$refs.hello.textContent) 
  }
}
</script>-->

<!--Refs-2-->

<template>
  <Hello ref="hello" />
</template>

<script>
import Hello from '~/components/Hello'

export default {
  components: {
    Hello
  },
  mounted() {
    // console.log(this.$refs.hello.$el)
    console.log(this.$refs.hello.$refs.good)
  }
}
</script>