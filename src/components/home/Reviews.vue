<template>
  <div style="margin-top: 40px">
    <!--<el-button @click="addArticle()">添加文章</el-button>-->
    <div class="articles-area">
      <el-card style="text-align: left">
        <div v-for="review in reviews" :key="review.id">
          <div style="float:left;width:85%;height: 150px;">
            <span style="font-size: 20px"><strong>{{review.title}}</strong></span>
            <el-divider content-position="left">{{review.date}}</el-divider>
           <p>{{review.content}}</p>
          </div>
          <el-image
            style="margin:18px 0 0 30px;width:100px;height: 100px"
            :src="review.cover"
            fit="cover"></el-image>
          <el-divider></el-divider>
        </div>
      </el-card>
    </div>
    <el-pagination
      background
      layout="total, prev, pager, next, jumper"
      @current-change="handleCurrentChange"
      :page-size="pageSize"
      :total="total">
    </el-pagination>
  </div>
</template>

<script>

export default {
  name: 'Articles',
  data () {
    return {
      reviews: [
        // eslint-disable-next-line standard/object-curly-even-spacing
        { 'id': 1, 'title': '东京平常日 1', 'content': '与书打交道的日常，这简直就是我的理想人生了。读松本老师的《东京平常日 1》就是重启人生本生！是将梦想放回原位，将每个人拉回最初开始地方的真诚呼唤。大家，大家，都要回到原来的地方才是啊～', 'cover': '../../../static/img/carousel/p4.jpg', 'date': '2024-05-09 04:41:03'},
        // eslint-disable-next-line standard/object-curly-even-spacing
        { 'id': 2, 'title': '北欧向左，美国向右？', 'content': '拉斯·特拉加德在美国居住期间逐渐意识到，自20世纪起，一直到步入21世纪，北欧社会的首要目标从来都不是要使经济“社会主义化”（人们经常误认为是这样）...', 'cover': '../../../static/img/carousel/p5.jpg', 'date': '2024-05-09 04:41:11'},
        // eslint-disable-next-line standard/object-curly-even-spacing
        { 'id': 3, 'title': '食南之徒', 'content': '如果一个人总是能带来美味的食物，他自然会赢得其他人的敬爱，这一点人类和其他动物并无区别。', 'cover': '../../../static/img/carousel/p6.jpg', 'date': '2024-05-09 04:44:03'}
      ],
      pageSize: 1,
      total: 0
    }
  }
  // mounted () {
  //   this.loadArticles()
  // },
  // methods: {
  //   loadArticles () {
  //     var _this = this
  //     this.$axios.get('/article/' + this.pageSize + '/1').then(resp => {
  //       if (resp && resp.data.code === 200) {
  //         _this.articles = resp.data.result.content
  //         _this.total = resp.data.result.totalElements
  //       }
  //     })
  //   },
  //   handleCurrentChange (page) {
  //     var _this = this
  //     this.$axios.get('/article/' + this.pageSize + '/' + page).then(resp => {
  //       if (resp && resp.data.code === 200) {
  //         _this.articles = resp.data.result.content
  //         _this.total = resp.data.result.totalElements
  //       }
  //     })
  //   }
  // }
}
</script>

<style scoped>
  .articles-area {
    width: 990px;
    height: 750px;
    margin-left: auto;
    margin-right: auto;
  }

  .article-link {
    text-decoration: none;
    color: #606266;
  }

  .article-link:hover {
    color: #409EFF;
  }
</style>
