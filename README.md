# mpvue-modal

> mpvue-modal is a excelent plugin base on mpvue.


## 用法

```html
<template>
  <div>
    <button @click="showHandler">点我打开</button>
    <comModal @closeModal="closeModal" :isShow="is_show">
      <span slot="title">我是标题</span>
      <div slot="content">
          我是内容
      </div>
    </comModal>
  </div>
</template>

<script>
import comModal from '@/components/modal'
export default {
  data () {
    return {
      is_show: false
    }
  },

  components: {
    comModal
  },

  methods: {
    closeModal(){
      this.is_show = false
    },
    showHandler () {
      this.is_show = true
    }
  },
  created() {

  }
}
</script>

```

## 参数说明

| 参数        | 说明                      | 类型      | 可选值  | 默认值    |
| ---------  | ----------------------- | ------- | ---- | ------ |
| isShow    | 控制显示隐藏     | Boolean | -    | false   |
| closeModal | 关闭弹框 | 事件 | - | - |

## 补充

- 使用过程中有任何问题，欢迎issue
