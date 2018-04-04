<template>
  <div>
    <button @click="showHandler">点我打开</button>
    <comModal @closeModal="closeModal" :isShow="is_show">
      <span slot="title">我是标题</span>
      <div slot="content">
        <div  v-for="(item,index) in 20" :key="index">
          我是内容
        </div>
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
      this.is_show = !this.is_show
    }
  },
  created() {

  }
}
</script>

<style>

</style>

