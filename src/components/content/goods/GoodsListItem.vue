<template>
  <div class="goods-item" @click="itemClick">
     <img :src="showImage" @load="imageLoad">
     <div class="goods-info">
       <p>{{goodsItem.title}}</p>
       <span class="price">￥{{goodsItem.price}}</span>
     </div>
  </div>
</template>

<script>
export default {
  name: 'GoodsListItem',
  data () {
    return {
      
    };
  },
  props:{
    goodsItem:{
      type: Object,
      default(){
        return []
      }
    }
  },
  computed: {
    showImage(){
      return this.goodsItem.image || this.goodsItem.show.img
    }
  },
  components: {
    
  },
  mounted () {
    
  },
  methods: {
    imageLoad(){
      // console.log('imageload');
      this.$bus.$emit('itemImageLoad')

      // if(this.$route.path.indexOf('/home')){
      //   this.$bus.$emit('homeItemImgLoad')
      // } else if(this.$route.path.indexOf('/detail')){
      //   this.$bus.$emit('detailItemImgLoad')
      // }
    },
    itemClick(){
      this.$router.push('detail/' + this.goodsItem.iid)
    }
  }
}
</script>
  
<style scoped>
  .goods-item {
    position: relative;
    width: 48%;
    padding-bottom: 40px;
  }
  .goods-item img {
    width: 100%;
  }
  .goods-info {
    position: absolute;
    bottom: 5px;
    left: 0;
    right: 0;
    font-size: 12px;
    overflow: hidden;
    text-align: center;
  }
  .goods-info p {
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    margin-bottom: 3px;
  }
  .goods-info .price {
    color: var(--color-high-text);
    margin-right: 20px;
  }
</style>