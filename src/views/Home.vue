<template>
  <div class="home">
    <aheader></aheader>
    <pre></pre>
    <div class="container" v-for="(item,index) in sliceArray(classmates,3)" :key="index">
      <div class="row">
        <div class="col" v-for="(item2,index2) in item" :key="index2">
          <card :name="item2.name" :content="item2.content"></card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Card from '@/components/Card.vue'
import Header from '@/components/Header.vue'

export default {
  name: 'Home',
  components: {
    card: Card,
    aheader: Header
  },
  data() {
    return {
      classmates: [
        {
          id: "0",
          name:"蔡徐坤",
          content: "我喜欢唱跳rap篮球"
        },
        {
          id: "1",
          name:"孙笑川",
          content: "你吼那么大声干什么嘛"
        },
        {
          id: "2",
          name:"岛市老八",
          content: "不管是香还是臭，到我嘴里都是块肉"
        }
      ]
    }
  },
  methods: {
    sliceArray:function(array, size){
      var result = [];
      for (var x = 0; x < Math.ceil(array.length / size); x++){
        var start = x * size;
        var end = start + size;
        result.push(array.slice(start,end));
      }
      return result;
    }
  }
}
</script>
