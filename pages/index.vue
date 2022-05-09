<template>
 <div>
   <features />
   <img-post />
 </div>
</template>

<script>
import features from '~/components/features.vue'
import ImgPost from '~/components/img-Post.vue'
export default {
  components: { features, ImgPost },
  name: 'IndexPage'
}
</script>
