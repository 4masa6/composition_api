<template>
  <div class="alert alert-primary">
    <h1>{{ title }}</h1>
    <p class="mt-3 h5">{{ data.msg }}</p>
  </div>
</template>

<script>
import { ref, reactive } from 'vue'

export default {
  props: {
    title: String
  },
  // contextはコンポーネントに関する情報をまとめたもの
  // attrs => コンポーネントタグに用意された属性をまとめたもの
  // slots => コンポーネント内に含まれるスロットをまとめたもの
  // emit  => emitされた内容をまとめたもの
  setup(props, context) {
    const data = reactive({
      msg: 'This is ref-value'
    })
    data.msg = context.attrs['msg'].toUpperCase()
    return {
      data
    }
  }
}
</script>
