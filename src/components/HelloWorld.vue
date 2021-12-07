<template>
  <div class="alert alert-primary">
    <h1>{{ title }}</h1>
    <p>{{ data.msg }} ({{ data.count }})</p>
  </div>
</template>

<script>
import { ref, reactive } from 'vue'

export default {
  props: {
    title: String,
  },
  setup(props) {
    const data = reactive({ // reactiveで作成できるのはオブジェクトのみ。数字や真偽値のようなものは使えない。
      // ｢基本型の値をリアクティブにしたいならref｣｢オブジェクトをリアクティブにするならreactive｣
      msg: 'This is ref-value!',
      count: 0
    })
    setInterval(() => {
      data.count++ // reactiveはrefと違って値をコピーして返すが、リアクティブになっている。valueを省略できる。
    }, 1000)
    return {
      data
    }
  }
}
</script>
