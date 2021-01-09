<template>
  <div id="Palbum">
    <div class="album">
      <img :src="imgList[0]" />
      <img :src="imgList[1]" />
      <img :src="imgList[2]" />
      <img :src="imgList[3]" />
    </div>
  </div>
</template>

<script>
export default {
  name: "Palbum",
  data() {
    return {
      imgList: [
        "http://pic2.zhimg.com/50/v2-4a06728efc99ba874a5d7422fd55aaed_hd.jpg",
        "http://img2.imgtn.bdimg.com/it/u=372764256,3394765004&fm=26&gp=0.jpg",
        "http://img1.imgtn.bdimg.com/it/u=1898582417,1582081952&fm=26&gp=0.jpg",
        "http://b-ssl.duitang.com/uploads/item/201707/10/20170710141316_vVFNh.thumb.700_0.jpeg"
      ]
    };
  }
};
</script>

<style scope>
.album img {
  width: 120px;
  height: 120px;
  margin-bottom: 10px;
  margin-left: 5px;
  margin-right: 5px;
}

.album {
  display: flex;
  flex-wrap: wrap;
  width: 260px;
}
</style> 