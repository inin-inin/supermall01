<template>
   <swiper class="detail-swiper">
      <swiper-item v-for="(item, index) in topImages" :key="index">
        <img :src="item">
      </swiper-item>
    </swiper>
</template>

<script>

import {Swiper,SwiperItem} from 'components/common/swiper'

export default {
  name: 'DetailSwiper',
  props: {
    topImages: {
      type: Array,
      default(){
        return []
      }
    }
  },
  data () {
    return {
      
    };
  },
  components: {
    Swiper,
    SwiperItem
  },
  mounted () {
    
  },
  methods: {
    
  }
}
</script>
  
<style scoped>
  .detail-swiper{
    /* width: 300px; */
    height: 400px;
  }
  .detail-swiper img{
    height:100%
  }
</style>