<template>
  <div>
    <Card>
      <b>网页大全</b>
      <Button type="info" @click="freeWeb" style="border-top-left-radius: 10px;margin-left: 10px">免费海贼王网站</Button>
      <Button type="info" @click="freeWeb" style="border-top-left-radius: 10px;margin-left: 10px">免费海贼王网站</Button>
      <Button type="primary" @click="freeWeb" style="border-top-left-radius: 10px;margin-left: 10px">免费海贼王网站</Button>
      <Button type="warning" @click="freeWeb" style="border-top-left-radius: 10px;margin-left: 10px">免费海贼王网站</Button>
      <Button type="dashed" @click="freeWeb" style="border-top-left-radius: 10px;margin-left: 10px">免费海贼王网站</Button>
      <Button type="default" @click="freeWeb" style="border-top-left-radius: 10px;margin-left: 10px">免费海贼王网站</Button>
    </Card>
  </div>
</template>
<script>
import DragList from '_c/drag-list'
import { getDragList } from '@/api/data'
export default {
  name: 'drag_list_page',
  components: {
    DragList
  },
  data () {
    return {
      list1: [],
      list2: [],
      dropConClass: {
        left: ['drop-box', 'left-drop-box'],
        right: ['drop-box', 'right-drop-box']
      },
      handleList: []
    }
  },
  methods: {
    handleChange ({ src, target, oldIndex, newIndex }) {
      this.handleList.push(`${src} => ${target}, ${oldIndex} => ${newIndex}`)
    },

    freeWeb () {
      window.location.href = 'https://www.qsptv.com/play/38018-1-1.html'
    }

  },
  mounted () {
    getDragList().then(res => {
      this.list1 = res.data
      this.list2 = [res.data[0]]
    })
  }
}
</script>
<style lang="less">
.drag-box-card{
  display: inline-block;
  width: 600px;
  height: 560px;
  .drag-item{
    margin: 10px;
  }
  h3{
    padding: 10px 15px;
  }
  .drop-box{
    border: 1px solid #eeeeee;
    height: 455px;
    border-radius: 5px;
  }
  .left-drop-box{
    margin-right: 10px;
  }
  .right-drop-box{
    //
  }
}
.handle-log-box{
  display: inline-block;
  margin-left: 20px;
  border: 1px solid #eeeeee;
  vertical-align: top;
  width: 200px;
  height: 500px;
  h3{
    padding: 10px 14px;
  }
  .handle-inner-box{
    height: ~"calc(100% - 44px)";
    overflow: auto;
    p{
      padding: 14px 0;
      margin: 0 14px;
      border-bottom: 1px dashed #eeeeee;
    }
  }
}
.res-show-box{
  display: inline-block;
  margin-left: 20px;
  border: 1px solid #eeeeee;
  vertical-align: top;
  width: 350px;
  height: 570px;
}
</style>
