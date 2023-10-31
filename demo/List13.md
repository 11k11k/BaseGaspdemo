# List13

## GSAP

1. 导入插件

   ```js
       <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
       <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
   ```

2. 编写代码

   ```js
    <script>
           ScrollTrigger.create({
               trigger: '.screen2',
               start: 'top top',
               end: '+=2500',
               scrub: true,
               markers: true, 
               //改为固定定位
               pin: true,
               animation:
                   gsap.timeline().fromTo('.black', { width: '100px', height: '100px' }, { width: '150px', height: '150px' })
                       .fromTo('.blue', { left: '55.124em' }, { left: '14.3em' }, "<")
                       .fromTo('.red', { right: '63.114em' }, { right: '14.3em' }, "<")
   
           })  
       </script>
   ```

## VIVO官网项目

1. 放大缩小

   ```js
   ScrollTrigger.create({
   start:'top top',
   end:'+=1000',
   srub:true,
   animation:
   gasp.timeline().fromTo('.one',{scale:1},{scale:0.5})
   .fromTo('.two',{},{},"<")
   })
   //当页面缩小，下个页面开始放大
   ```

2. 使用滚动条控制视频播放

   ```js
   ScrollTrigger.create({
   start:'top top',
   end:'+=4000',
   srub:true,
   pin:true,
   animation(){
   const summary=document.querySelector('.summary')
   try{
   //self.progress:滚动的整体进度
   //summary.duration:视频的总时长
   //
   summary.currentTime=self.progress*summary.duration
   }
   catch(e)
   {console.log(e)}
   }
   })
   ```

3. 播放视频

   ```js
   ScrollTrigger.create({
   start:'top top',
   end:'+=4000',
   srub:true,
   
   animation:
   gsap.timeline()
   .fromTo('.title',{opacity:1},{opacity:0})
   .fromTo('video1',
   {
   'margin-top':"100%"
   },
   {
   "margin-top":0,
   
   onStart()
   {
   const video1=document.querySelector('.video1')
   video1.currentTime=0//从开头开始
   vide01.play()//开始播放
   }
   }
   )
   })
   ```

   







