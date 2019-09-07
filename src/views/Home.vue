<template>
  <div class="home">
    <header>
    <ul class="nav">
     <li v-for="(item,index) in itemss " :key='index'>{{item.nav}}</li>
     <li class="Select"> Select Location</li>
     <li class="login">登录</li>
     <li>注册</li>
     <li>消息通知</li>
     <li class="shopping"  @mouseenter="flag=true"  @mouseleave="flag=false" :class="flag==true?'show':''">购物车</li>
      <ul class="shopping-mb" v-if="flag">
      sfsb
     </ul>
    </ul>
    </header>
    <div class="count">
      
      <ul class="count-nav">
         <img src="https://s02.mifile.cn/assets/static/image/mi-logo.png" alt=""  style="width:46px;height:46px;background: orangered;padding:3px;">
            <ul class="nav-list">
                <li   v-for="(item,index) in items" :key='index' @mouseenter="isshow=true" @mouseleave="isshow=false"  >{{item.title}}</li>
             </ul>
             <ul>
              <input type="text" style="height:48px;width:250px">
             <input type="button" value="确定"  style="height:54px;width:50px">
             </ul>
        </ul>
         <div class="banner">
            <img  v-for="(v,i) in img " :key="i" :src="v" v-show="i==n" class="img"/>   
            <div class="banner-circle">
                <ul>
                    <li  v-for="(v,i) in img " :key="i" :class="i==n ?'selected':''"></li>  
                </ul> 
            </div>
        </div>
        <!-- 第二个列表蒙版 -->
        <ul class="nav-list-mb"  v-if="isshow">
         </ul>

         <div style="width:100%; display: flex;justify-content: space-between; position: relative;">
            <ul class="list-three">
                <li   v-for="(item,index) in s" :key='index'  @click="flag2=!flag2"  >{{item.nr}}<span>></span></li>
             </ul>
         <ul class="flag2-mb"  v-if="flag2">
           11111111111111111111111111111111111111111111111111
         </ul>
         </div>
            <ul style="display: flex;">
               <ul class="p">
                    <li  class="el-icon-edit">小米秒杀</li>
                    <li class="el-icon-shopping-cart-2">小米秒杀</li>
                    <li>小米秒杀</li>
                    <li>小米秒杀</li>
                    <li>小米秒杀</li>
                    <li>小米秒杀</li>
                 </ul>
                <img :src="picture" alt=""  v-for="picture in pictures" :key="picture" class="p picture">
             </ul> 
             
             <div style="width:100%;">
                  <p style="font-size:22px;">小米闪购</p>
                   <div style="display: flex;justify-content: space-between">
                     <ul class='ul'>
                      <h3 style="color:red; text-align:center;margin:50px 0px">00:00场</h3>
                      <img src="../assets/1.png" alt="" style="margin:0px 110px">
                      <p style="text-align:center;margin-top:20px;">距离结束还有</p>
                      <div style="display: flex;justify-content: space-around;margin-top:20px">
                          <li class="libg" v-for="n in 3" :key='n'>11 </li>
                      </div>
                   </ul>
                   <ul  class='ul ul2' v-for="pic in pics" :key='pic'   >
                   <img :src="pic.url" alt="" >
                   <p class="title">{{pic.title}}</p>
                   <p class="title pic">{{pic.money}}</p>
                  </ul>
                  </div>
                  <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/1a2f39c9fe0804ace1d3707574c7c86f.jpg?thumb=1&w=1533&h=150&f=webp&q=90" alt="" style="width:100%;margin:30px 0px">
                  </div>
                      <p style="font-size:22px;margin-bottom:20px">手机</p>
                      <div style=" display: flex;  justify-content: space-between; flex-wrap: wrap">
                        <ul style="width:295px">
                          <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/79ed6663b57e30554a5d1f0653c68b78.jpg?thumb=1&w=293&h=768&f=webp&q=90" alt="" >
                         </ul>
                         <ul style="width:960px;display: flex; flex-wrap: wrap">
                                 <ul  style="width:220px;height:360px;border:1px red solid;margin-left:18px;" v-for="img in imgs" :key='img'   >
                                     <img :src="img.url" alt="" style="width:220px">
                                     <p class="title">{{img.title}}</p>
                                      <p class="title">{{img.title2}}</p>
                                     <p class="title pic">{{img.pic}}</p>
                                </ul>
                         </ul>
                         <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/33cedc66dd2657967f725c6c0a30d4ca.jpg?thumb=1&w=1533&h=150&f=webp&q=90" alt="" style="width:100%;margin:30px 0px">
                      </div>
                       <p style="font-size:22px;margin-bottom:20px">家电</p>
                      <div style=" display: flex;  justify-content: space-between; flex-wrap: wrap">
                        <ul style="width:295px;">
                          <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/b56fd90a60e3d9e5d87dae9fbd427ea8.jpg?thumb=1&w=293&h=375&f=webp&q=90" alt="" >
                          <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/b67de5a8ce9025fb5d8bac66e019d1c3.jpg?thumb=1&w=293&h=375&f=webp&q=90" alt="" >
                         </ul>
                         <ul style="width:960px;display: flex; flex-wrap: wrap">
                                 <ul  style="width:220px;height:360px;border:1px red solid;margin-left:18px;" v-for="img in imgs2" :key='img'   >
                                     <img :src="img.url" alt="" style="width:220px">
                                     <p class="title" style="font-size:14px">{{img.title}}</p>
                                      <p class="title" style="font-size:14px;">{{img.title2}}</p>
                                     <p class="title pic">{{img.pic}}</p>
                                </ul>
                         </ul>
                         <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/d0e4830afe0de0fb41b187a0dd034057.jpg?thumb=1&w=1533&h=150&f=webp&q=90" alt="" style="width:100%;margin:30px 0px">
                      </div>
                       <p style="font-size:22px;margin-bottom:20px">智能</p>
                      <div style=" display: flex;  justify-content: space-between; flex-wrap: wrap">
                        <ul style="width:295px;">
                          <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/45c23f5b9a927b2dc49c25277e07727c.jpg?thumb=1&w=293&h=375&f=webp&q=90" alt="" >
                          <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/a660ce095e8f553a9ed1515265f4e9fc.jpg?thumb=1&w=293&h=375&f=webp&q=90" alt="" >
                         </ul>
                         <ul style="width:960px;display: flex; flex-wrap: wrap">
                                 <ul  style="width:220px;height:360px;border:1px red solid;margin-left:18px;" v-for="img in imgs2" :key='img'   >
                                     <img :src="img.url" alt="" style="width:220px">
                                     <p class="title" style="font-size:14px">{{img.title}}</p>
                                      <p class="title" style="font-size:14px;">{{img.title2}}</p>
                                     <p class="title pic">{{img.pic}}</p>
                                </ul>
                         </ul>
                         <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/0e2cf7dd837eb8d4690070d7dfa817d9.jpg?thumb=1&w=1533&h=150&f=webp&q=90" alt="" style="width:100%;margin:30px 0px">
                      </div>
                          <p style="font-size:22px;margin-bottom:20px">搭配</p>
                      <div style=" display: flex;  justify-content: space-between; flex-wrap: wrap">
                        <ul style="width:295px;">
                          <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/6874615b3c50e837ffe532eb6ea4ef1a.jpg?thumb=1&w=293&h=375&f=webp&q=90" alt="" >
                          <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/e4e456617d58227cc70d682b42fe90e3.jpg?thumb=1&w=293&h=375&f=webp&q=90" alt="" >
                         </ul>
                         <ul style="width:960px;display: flex; flex-wrap: wrap">
                                 <ul  style="width:220px;height:360px;border:1px red solid;margin-left:18px;" v-for="img in imgs2" :key='img'   >
                                     <img :src="img.url" alt="" style="width:220px">
                                     <p class="title" style="font-size:14px">{{img.title}}</p>
                                      <p class="title" style="font-size:14px;">{{img.title2}}</p>
                                     <p class="title pic">{{img.pic}}</p>
                                </ul>
                         </ul>
                         <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/89c2a209b742fce9b10d9d196149d634.jpg?thumb=1&w=1533&h=150&f=webp&q=90" alt="" style="width:100%;margin:30px 0px">
                      </div>
                        <p style="font-size:22px;margin-bottom:20px">配件</p>
                      <div style=" display: flex;  justify-content: space-between; flex-wrap: wrap">
                        <ul style="width:295px;">
                          <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/739ebd8abfc2b1be8866a2c1ad87e709.jpg?thumb=1&w=293&h=375&f=webp&q=90" alt="" >
                          <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/ffe4182f1d9a5befdf2380ec90ae1620.jpg?thumb=1&w=293&h=375&f=webp&q=90" alt="" >
                         </ul>
                         <ul style="width:960px;display: flex; flex-wrap: wrap">
                                 <ul  style="width:220px;height:360px;border:1px red solid;margin-left:18px;" v-for="img in imgs2" :key='img'   >
                                     <img :src="img.url" alt="" style="width:220px">
                                     <p class="title" style="font-size:14px">{{img.title}}</p>
                                      <p class="title" style="font-size:14px;">{{img.title2}}</p>
                                     <p class="title pic">{{img.pic}}</p>
                                </ul>
                         </ul>
                         <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/10fb0086cb21120c53248a3d8cc56dc5.jpg?thumb=1&w=1533&h=150&f=webp&q=90" alt="" style="width:100%;margin:30px 0px">
                      </div>
                          <p style="font-size:22px;margin-bottom:20px">周边</p>
                      <div style=" display: flex;  justify-content: space-between; flex-wrap: wrap">
                        <ul style="width:295px;">
                          <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/99f1f43d9df484572bd81138f45dfc0f.jpg?thumb=1&w=293&h=375&f=webp&q=90" alt="" >
                          <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/e0b8cffcbdaa88e2a314f0a372ca75dd.jpg?thumb=1&w=293&h=375&f=webp&q=90" alt="" >
                         </ul>
                         <ul style="width:960px;display: flex; flex-wrap: wrap">
                                 <ul  style="width:220px;height:360px;border:1px red solid;margin-left:18px;" v-for="img in imgs2" :key='img'   >
                                     <img :src="img.url" alt="" style="width:220px">
                                     <p class="title" style="font-size:14px">{{img.title}}</p>
                                      <p class="title" style="font-size:14px;">{{img.title2}}</p>
                                     <p class="title pic">{{img.pic}}</p>
                                </ul>
                         </ul>
                         <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/88e35cffc82cd98cd53172460067af17.jpg?thumb=1&w=1533&h=150&f=webp&q=90" alt="" style="width:100%;margin:30px 0px">
                      </div>
                        <p style="font-size:22px;margin-bottom:20px">视频</p>
                        <div style=" display: flex;justify-content: space-between">
                                <ul style="width:300px;height:260px;border:1px red solid"  v-for="s in 4" :key="s">
                                    <img src="https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/3a134c9f8fffb85a47ac397e7eeba7e8.jpg?thumb=1&w=370&h=225&f=webp&q=90" alt="" style="width:300px">
                                    <p style="text-align:center;margin-top:25px;font-size:18px"> Redmi Note 8 系列发布会 </p>
                                </ul>
                        </div>
                        <div style="width:1270px;height:400px;margin:0px auto;">
                        <ul class="foot-nav">
                           <li>预约维修服务</li>
                           <li>预约维修服务</li>
                           <li>预约维修服务</li>
                           <li>预约维修服务</li>
                           <li>预约维修服务</li>
                            <li>520余家售后网点</li>
                        </ul>
                        <div style="display: flex">
                           <ul class="foot">
                           <li> <p style="margin:20px 0px ;font-size:18px;">帮助中心</p><p>帮助中心</p><p>帮助中心</p><p>帮助中心</p>  </li>
                           <li><p style="margin:20px 0px ;font-size:18px;">服务支持</p><p>帮助中心</p><p>帮助中心</p><p>帮助中心</p> </li>
                           <li><p style="margin:20px 0px ;font-size:18px;">线下门店</p><p>帮助中心</p><p>帮助中心</p><p>帮助中心</p></li>
                           <li><p style="margin:20px 0px ;font-size:18px;">线下门店</p><p>帮助中心</p><p>帮助中心</p><p>帮助中心</p></li>
                           <li><p style="margin:20px 0px ;font-size:18px;">线下门店</p><p>帮助中心</p><p>帮助中心</p><p>帮助中心</p></li>
                            <li><p style="margin:20px 0px ;font-size:18px;">线下门店</p><p>帮助中心</p><p>帮助中心</p><p>帮助中心</p></li>
                        </ul>
                         <ul class="foot one">
                           <div style="width:100%;margin:10px 30px">
                           <p style="color:red;font-size: 21px;height:25px;margin:10px 0px">400-100-5678</p>
                           <p style="margin:10px 0px;font-size:14px">周一至周日 8:00-18:00</p>
                           <p style="margin:10px 20px;font-size:14px">（仅收市话费）</p>
                          <p  style="width:80px;border:1px black solid;padding:7px;text-align:center;margin:0px 25px" >联系人工</p>
                           </div>
                        </ul>
                        </div>
                        <div></div>
                      
                                   <div style="width:100%;height:300px;background:grey">
                           <ul  class="nav4">
                                <li>小米商城</li>
                                <li>小米商城</li>
                                <li>小米商城</li>
                                <li>小米商城</li>
                                <li>小米商城</li>
                                <li>小米商城</li>
                                <li>小米商城</li>
                                <li>小米商城</li>
                                <li>小米商城</li>
                                <li>小米商城</li>
                                <li>小米商城</li>
                                <li>小米商城</li>
                                 <li>小米商城</li>
                                <li>小米商城</li>
                                <li>小米商城</li>
                           </ul>
                               <ul  class="nav4" style="margin-top:10px">
                                    <li>© mi.com 京ICP证110507号</li>
                                    <li> 京ICP备10046444号 </li>
                                     <li> 京公网安备11010802020134号 </li>
                                     <li> 京网文[2017]1530-131号 </li>
                           </ul>
                             <ul  class="nav4" >
                                     <li>（京）网械平台备字（2018）第00005号 <li>
                                      <li>互联网药品信息服务资格证 (京) -非经营性-2014-0090 </li>
                                      <li> 营业执照 </li>
                                     <li>  医疗器械公告</li>
                           </ul>
                             <ul  class="nav4" >
                                     <li>增值电信业务许可证 </li>
                                     <li>网络食品经营备案（京）【2018】WLSPJYBAHF-12</li>
                                     <li>  食品经营许可证</li>
                           </ul>
                           <p>违法和不良信息举报电话：185-0130-1238 知识产权侵权投诉 本网站所列数据，除特殊说明，所有数据均出自我司实验室测试</p>
                         

                         </div>
                        
                        </div>
                  
                     
         
       
       
       </div>
  </div>
</template>

<script>
export default {
   methods:{
        fun:function(){
            //setInterval(函数体,时间)
            setInterval(this.play,2000)
        },
        play:function(){
            this.n++;
            if(this.n == this.img.length){
                this.n = 0;
            }
        }
    },
    mounted:function(){    //生命周期  钩子函数   挂载完成
        this.fun()
    }, 
  data () {
    return {
     flag:false,
     isshow:false,
     flag2:false,
      n: 0,
      img:[
            
            'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/a12c020bb78f75af14f5de2a761631f4.jpg?thumb=1&w=1533&h=575&f=webp&q=90',
            'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/e52c3e98602b90f198ec316dce253cba.jpg?thumb=1&w=1533&h=575&f=webp&q=90',
            'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/a12c020bb78f75af14f5de2a761631f4.jpg?thumb=1&w=1533&h=575&f=webp&q=90',
            'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/64866b83bc34a5b54d022417910d715d.jpg?w=2452&h=920',
            'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/a12c020bb78f75af14f5de2a761631f4.jpg?thumb=1&w=1533&h=575&f=webp&q=90',
            'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/e52c3e98602b90f198ec316dce253cba.jpg?thumb=1&w=1533&h=575&f=webp&q=90',
            ],
     itemss:[
       {nav:'小米商城', id:1},
       {nav:'MIUI', id:1},
       {nav:'IoT', id:1},
       {nav:'云服务', id:1},
        {nav:'金融', id:1},
         {nav:'有品', id:1},
        {nav:'小爱开放平台', id:1},
        {nav:'企业团购', id:1},
        {nav:'资质证照', id:1},
        {nav:'协议规则', id:1},
        {nav:'下载app', id:1},
     ],
     items:[
       {title:'小米手机',id:0},
       {title:'Readmi红米',id:1},
        {title:'电视',id:2},
        {title:'笔记本',id:3},
        {title:'家电',id:4},
        {title:'路由器',id:5},
        {title:'智能硬件',id:6},
        {title:'服务',id:7},
        {title:'社区',id:8},
     ],
    s:[
      {nr:'手机 电话卡'},
      {nr:'手机 电话卡'},
      {nr:'手机 电话卡'},
      {nr:'手机 电话卡'},
      {nr:'手机 电话卡'},
      {nr:'手机 电话卡'},
      {nr:'手机 电话卡'},
      {nr:'手机 电话卡'},
      {nr:'手机 电话卡'},
      {nr:'手机 电话卡'},

    ],
    pictures:[
      'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/37d52be5170e1b25d30ff44db4b0791c.jpg?w=632&h=340',
      'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/e7b51b721c3319e9c2916cc41cd9c695.jpg?w=632&h=340',
      'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/816a66edef10673b4768128b41804cae.jpg?w=632&h=340'
    ],
    pics:[
      {url:'https://i8.mifile.cn/v1/a1/0a872a83-a929-7e0d-1892-cf28b0d75077!250x250.jpg',title:'米家智能门锁 霸王锁体 碳素黑',money:'1111元'},
      {url:'https://i8.mifile.cn/v1/a1/0a872a83-a929-7e0d-1892-cf28b0d75077!250x250.jpg',title:'米家智能门锁 霸王锁体 碳素黑',money:'1111元'},
      {url:'https://i8.mifile.cn/v1/a1/0a872a83-a929-7e0d-1892-cf28b0d75077!250x250.jpg',title:'米家智能门锁 霸王锁体 碳素黑',money:'1111元'},

    ],
    imgs:[
      {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/6f2493e6c6fe8e2485c407e5d75e3651.jpg',title:'Redmi Note 8 Pro',title2:'6400万全场景四摄',pic:'1399元'},
       {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/6f2493e6c6fe8e2485c407e5d75e3651.jpg',title:'Redmi Note 8 Pro',title2:'6400万全场景四摄',pic:'1399元'},
        {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/6f2493e6c6fe8e2485c407e5d75e3651.jpg',title:'Redmi Note 8 Pro',title2:'6400万全场景四摄',pic:'1399元'},
         {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/6f2493e6c6fe8e2485c407e5d75e3651.jpg',title:'Redmi Note 8 Pro',title2:'6400万全场景四摄',pic:'1399元'},
          {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/6f2493e6c6fe8e2485c407e5d75e3651.jpg',title:'Redmi Note 8 Pro',title2:'6400万全场景四摄',pic:'1399元'},
           {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/6f2493e6c6fe8e2485c407e5d75e3651.jpg',title:'Redmi Note 8 Pro',title2:'6400万全场景四摄',pic:'1399元'},
            {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/6f2493e6c6fe8e2485c407e5d75e3651.jpg',title:'Redmi Note 8 Pro',title2:'6400万全场景四摄',pic:'1399元'},
           {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/6f2493e6c6fe8e2485c407e5d75e3651.jpg',title:'Redmi Note 8 Pro',title2:'6400万全场景四摄',pic:'1399元'},
    ],
      imgs2:[
      {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8ce424d6fe93dfb74733b5838140b7ee.jpg?thumb=1&w=250&h=250&f=webp&q=90',title:' 米家互联网空调C1（一级能效） ',title2:'1.5匹变频，自清洁，节能省电',pic:'2599元'},
      {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8ce424d6fe93dfb74733b5838140b7ee.jpg?thumb=1&w=250&h=250&f=webp&q=90',title:' 米家互联网空调C1（一级能效） ',title2:'1.5匹变频，自清洁，节能省电',pic:'2599元'},
      {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8ce424d6fe93dfb74733b5838140b7ee.jpg?thumb=1&w=250&h=250&f=webp&q=90',title:' 米家互联网空调C1（一级能效） ',title2:'1.5匹变频，自清洁，节能省电',pic:'2599元'},
      {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8ce424d6fe93dfb74733b5838140b7ee.jpg?thumb=1&w=250&h=250&f=webp&q=90',title:' 米家互联网空调C1（一级能效） ',title2:'1.5匹变频，自清洁，节能省电',pic:'2599元'},
      {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8ce424d6fe93dfb74733b5838140b7ee.jpg?thumb=1&w=250&h=250&f=webp&q=90',title:' 米家互联网空调C1（一级能效） ',title2:'1.5匹变频，自清洁，节能省电',pic:'2599元'},
      {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8ce424d6fe93dfb74733b5838140b7ee.jpg?thumb=1&w=250&h=250&f=webp&q=90',title:' 米家互联网空调C1（一级能效） ',title2:'1.5匹变频，自清洁，节能省电',pic:'2599元'},
      {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8ce424d6fe93dfb74733b5838140b7ee.jpg?thumb=1&w=250&h=250&f=webp&q=90',title:' 米家互联网空调C1（一级能效） ',title2:'1.5匹变频，自清洁，节能省电',pic:'2599元'},
      {url:'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/8ce424d6fe93dfb74733b5838140b7ee.jpg?thumb=1&w=250&h=250&f=webp&q=90',title:' 米家互联网空调C1（一级能效） ',title2:'1.5匹变频，自清洁，节能省电',pic:'2599元'},
    ],
    }
  },

}
</script>
<style >
*{
  margin: 0px;
  padding: 0px;
}
.home{
    overflow:hidden;   
}
header{
  width:100%;
  background: rgb(51, 49, 49);
 
}
.nav{
  width: 1270px;
  height: 40px;
  margin: 0px auto;
   background: rgb(51, 49, 49);
   position: relative;
}
.nav li{
  max-height: 45px;
  line-height: 40px;
  list-style: none;
  padding: 0px 11px;
  color: white;
  display: inline-block;
  border-right: 1px orange solid;
  font-size: 11px;
  color: #b0b0b0;
  cursor: pointer;

}
 .Select{
  border: none;
 }
.login{
  margin-left: 230px !important;
}
.shopping{
  width:100px;
  line-height: 40px !important;
  background: #424242;
  text-align: center;
}
.shopping-mb{
  width: 350px;
  height: 100px;
  background: black;
  position: absolute;
  right: 0px;
  z-index: 33;
}
.count{
  width:1270px;
  margin: 0px auto;

}
.show{
  background: white;
  color: red !important;
 
}
.count-nav{
  width:100%;
  height: 100px;
  display: flex; 
  align-items: center;
  justify-content: space-between;
  background: white;
  position: relative;
}
.nav-list li{
  list-style: none;
  display: inline-block ;
  font-size: 17px;
  padding: 10px;
  cursor: pointer;
}
.nav-list-mb{
  width:1270px;
  height: 200px;
  background: red;
  position: absolute;
  top: 140px;
  z-index: 66
}
.list-three{
  position: absolute;
  top: -460px;
  width:250px;
  height:460px;
  background: rgb(168, 160, 160);
  opacity: 0.6;
  z-index: 4;

}
.list-three li{
  width:250px;
  height: 45px;
  line-height: 45px;
  text-align: center;
  display: flex;
  justify-content: space-around;
  color: white;
  cursor: pointer;
 
}
.flag2-mb{
  width:1020px;
  height:460px;
  background: white;
  border: 1px red solid;
  position: absolute;
  top: -460px;
  left: 250px;

}
.banner {
    position: relative;
    display: flex;
    justify-content: flex-end;
    width: 100%;
   
}
.banner .banner-circle {
    position: absolute;
    bottom: 5px;
    left: 0;
    right: 0;
    color: #fff;
}
.banner .banner-circle li{
    display:inline-block;
    background: rgba(0,0,0,.3);
    border-radius: 50%;
    padding:6px;
    margin:2px;
}
.banner .banner-circle ul {
    text-align: right;
    margin-right: 30px;
}
.banner .banner-circle .selected {
    background: rgba(0,0,0,.8);
}
 .img {
  width: 100%;
  height: 460px;
    margin: 0;
    padding: 0;
    
}
.p{
  margin: 15px 0px;
  width:250px;
  height:180px;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  background: rgb(80, 76, 76);
}
.p li{
  list-style: none;
  border: 1px white solid;
  width:80px;
  line-height: 80px;
  text-align: center;
  color: white;
  cursor: pointer;
  
  
}
.picture{
  width:325px;
  margin-left: 15px;
  cursor: pointer;
}
.libg{
list-style: none;
width:50px;
height:50px;
background: black;
color:white;
font-size: 18px;
line-height: 50px;
text-align: center;


}
.ul{
 width:250px;
 height:330px;
 margin-top:10px;
 border:1px red solid;
 background: rgb(199, 175, 175)
}
.ul2{
  background: none;
 border: 1px solid orangered
}
.title{
  width:100%;
  text-align:center;
  margin-top: 10px;
}
.pic{
  color:red
}
.foot-nav{
  margin-top: 20px;
  width:100%;
  border-bottom:1px red solid;
  display: flex;
  justify-content: space-around;
  background: skyblue

}
.foot-nav li{
  margin: 15px 0px;
  list-style: none;
  width:160px;
  height:40px;
  line-height: 40px;;
  border-right: 1px red solid;
  text-align: center;


}
.foot{
  width:1040px;
  height:180px;
  border-right: 1px black solid;
  list-style: none;
  display: flex;
  background: skyblue
}
.foot li{
  width:200px;
  height:180px;
  text-align: center;
}
.one{
  width:240px;
  height:180px;
 
}
.nav4{
list-style:none;
display: flex;
flex-wrap: wrap;
}
.nav4 li{
  font-size: 14px;
  padding: 3px 10px;
  border-right: 1px red solid;
}

 
</style>
