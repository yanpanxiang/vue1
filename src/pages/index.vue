<template>
  <div class="index-wrap">
      <div class="index-left">
        <div class="index-left-block">
            <h2>全部产品</h2>
            <template v-for="(product, index) in productList">
                <h3 :key="index">{{ product.title}}</h3>
                <ul :key="index">
                    <li v-for="item in product.list">
                        <a :href="item.url">{{item.name}}</a>
                        <span v-if="item.hot" class="hot-tag">HOT</span>
                    </li>
                </ul>
                <div :key="index" v-if="!product.last" class="hr"></div>
            </template>
        </div>
      </div>
      <div class="index-right">

      </div>
  </div>
</template>



<script>
    export default {
        data () {
            return {
                productList: {
                    pc: {
                        title : 'pc产品',
                        list : [
                           {
                            name: '数据统计',
                            url: 'http://starcraft.com'
                            },
                            {
                            name: '数据预测',
                            url: 'http://warcraft.com'
                            },
                            {
                            name: '流量分析',
                            url: 'http://overwatch.com',
                            hot: true
                            },
                            {
                            name: '广告发布',
                            url: 'http://hearstone.com'
                            }
                        ]
                    },
                    app: {
                        title : '应用类',
                        last : true,
                        list : [
                            {
                            name: '91助手',
                            url: 'http://weixin.com'
                            },
                            {
                            name: '产品助手',
                            url: 'http://twitter.com',
                            hot: true
                            },
                            {
                            name: '智能地图',
                            url: 'http://maps.com'
                            },
                            {
                            name: '团队语音',
                            url: 'http://phone.com'
                            }
                        ]
                    }
                }
            }
        }
    }
</script>


<style lang="scss" scoped>
    .index-wrap{
        overflow: hidden;
        .index-left{
            float: left;
            width: 300px;
            text-align: left;
            .index-left-block{
                margin: 15px;
                background: #ffffff;
                box-shadow: 0 0 1px #ddd;
                .hr{
                    margin-bottom: 20px;
                }
                h2{
                    background: #4fc08d;
                    color: #ffffff;
                    padding: 10px 15px;
                    margin-bottom: 20px; 
                }
                h3{
                    padding: 0 15px 5px 15px;
                    font-weight: bold;
                    color: #222;
                }
                ul{
                    padding: 10px 15px;
                    li{
                        padding: 5px;
                        .hot-tag{
                            background: red;
                            color: #fff;
                        }
                    }
                }
            }
        }
        .index-right{
            float: right;
            width: 900px;
        }
    }
</style>

