<template>
  <div class="warp">
			<div class="show">
				
			</div>
			<div class="content">
				<div class="text-area">
					<div class="title">{{title}}</div>
					<div class="swiperBox">
						<van-swipe class="swiper" indicator-dots indicator-active-color='#fff' :autoplay='5000' loop :duration="500">
							<van-swipe-item v-for="(item,index) in project" :key='index'>
								<div class="swiperTitle">
									{{item.name}}
								</div>
								<div class="swiper-item-image">
									<van-image :src="item.url" :fit="item.mode"/>
								</div>
								<div class="swiperTitle">
									{{item.introduce}}
								</div>
							</van-swipe-item>
							
						</van-swipe>
					</div>
					<div class="info">
						<div class="code">
							<van-image :src="code" fit="fill"/>
						</div>
						<div class="text">
							<div>长按扫码 联系我</div>
							<div>永久维护</div>
							<div>联系方式 微信同号13826111068</div>
						</div>
					</div>
				</div>
			</div>
		
	</div>
</template>

<script  lang="ts">
// @ is an alias to /src
import Vue from 'vue';
import Component from 'vue-class-component';
import 'vant/lib/index.css';
import { Swipe, SwipeItem,Image as VanImage} from 'vant';

Vue.use(Swipe);
Vue.use(SwipeItem);
@Component({
  components: { Swipe,SwipeItem,VanImage}
})
  export default class App extends Vue {

    // 初始化数据
  title='项目介绍';
  project=[
    {
      url:require('@/image/gongxiangshizi.png'),
      type:0,
      requireUrl:"https://www.litakeji.com/#/home",
      name:"共享师资官网",
      introduce:'一个做可直播的授课平台',
      mode:'fill'
    },
    {
      url:require('@/image/jiaxin.png'),
      type:0,
      requireUrl:"http://crm.jiaxqiye.com",
      name:"嘉信招商自动化系统",
      introduce:'一个关于公司管理的平台',
      mode:'fill'
    },
    {
      url:require('@/image/myt.png'),
      type:1,
      requireUrl:"https://www.litakeji.com/#/home",
      name:"搬金蚁小程序",
      introduce:'',
      mode:'fill'
    }
  ];
  code=require('@/image/code.png');
  msg = 123;

    // 声明周期钩子
  mounted () {
      // this.greet()
    }

    // 计算属性
    get computedMsg () {
      return 'computed ' + this.msg
    }

  

    // 方法
  //  onClickLeft () {
  //     Toast('返回');
  //   }

  //   onClickRight () {
  //     Toast('按钮');
  //   }

  //   greet () {
  //     Toast('返回');
  //   }
    
  }

</script>
<style lang='scss'>
img{
		width: 100%;
		height: 100%;
	}
	.warp{
		/* position: absolute; */
		font-size: 0.42rem;
		}
		.show{
			width: 100%;
			height: 9rem;
			background: url(../image/pic.png) no-repeat;
			background-size: 100% 100%;
		}
	.content {
		display: flex;
		/* flex-direction: column; */
		justify-content: center;
		background: #1C2630;
		padding: 0 .25rem 2rem;	
		/* position: relative; */
		/* position: fixed; */
		width: 100%;
		/* height: 700rem; */
		
		box-sizing: border-box;
	}

	.text-area {
		/* display: flex;
		justify-content: center; */
		background: #FFFFFF;
		width: 100%;
		border-radius:.2rem ;
		padding: .25rem .25rem ; 
		box-sizing: border-box;
	}

	.title {
		font-size: 0.42rem;
		color: #fff;
		width: 3rem;
		height: .85rem;
		margin: 0 auto;
		background: url(../image/title.png) no-repeat ;
		background-size: 100% 100%;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.swiperBox{
		height: 7rem;
		width: 100%;
		padding:.5rem 0 ;
		box-sizing: border-box;
		text-align: center;
		color: #007AFF;
		
	}
	.swiper{
		height: 100%;
	}
	.swiper-item-image{
		width: 100%;
    padding:.2rem 0;
		/* height: 650rem; */
		
	}
	.info{
		display: flex;
		justify-content: center;
		align-items: center;
		padding: .3rem;
		box-sizing: border-box;
		background: #508DF3;
		border-radius: .2rem;
		color: #fff;
	}
	.code{
		width: 2rem;
		height: 1.5rem;
		}
		.text{
			padding-left: .30rem;
		}
</style> 
