# Front-end-interview
#### 页面布局
###  题目：假设高度已知，请写出三栏布局，其中左栏、右栏宽度各位300px，中间自适应。
     浮动布局
     <style>
      html *{
        padding:0;
        margin:0;
      }
      .layout article div{
         min-height:100px;
      }
      .layout.float .left{
         float:left;
         width:300px;
         background:red;
      }
      .layout.float .right{
         float:right;
         width:300px;
         background:blue;
      }
      .layout.float .center{ 
         background:yellow;
      }
     </style>
     <section class="layout float">
        <article class="left-right-center">
          <div class="left"></div>
          <div class="right"></div>
          <div class="center">
            <h1>dfdfd</h1>
          </div>
        </article>
     </section>
     //绝对布局
     <style>
      html *{
        padding:0;
        margin:0;
      }
      .layout article div{
         min-height:100px;
         position:absoluete;
      }
      .layout.absolute .left{
         left:0;
         width:300px;
         background:red;
      }
      .layout.absolute .right{
         right:300px;
         width:300px;
         background:blue;
      }
      .layout.float .center{ 
         left:300px;
         right:300px;
         background:yellow;
      }
     </style>
     <section class="layout absolute">
        <article class="left-right-center">
          <div class="left"></div>
          <div class="right"></div>
          <div class="center">
            <h1>dfdfd</h1>
          </div>
        </article>
     </section>
     //flex布局
        <style>
        html *{
          padding:0;
          margin:0;
        }
        .layout article div{
           min-height:100px;
        }
        .layout article{
          display:flex;
        }
        .layout.flex .left{
           left:0;
           width:300px;
           background:red;
        }
        .layout.flex .right{
           right:300px;
           width:300px;
           background:blue;
        }
        .layout.flex .center{ 
           flex:1;
           background:yellow;
        }
      </style>
         <section class="layout flex">
          <article class="left-right-center">
            <div class="left"></div>
            <div class="center">
              <h1>dfdfd</h1>
            </div>
            <div class="right"></div>
          </article>
       </section>
       //table布局
        <style>
        html *{
          padding:0;
          margin:0;
        }
        .layout article div{
           min-height:100px;
           display:table-cell
        }
        .layout article{
          display:table;
        }
        .layout.table .left{
           width:300px;
           background:red;
        }
        .layout.table .right{
           width:300px;
           background:blue;
        }
        .layout.table .center{
           background:yellow;
        }
      </style>
         </style>
         <section class="layout table">
          <article class="left-right-center">
            <div class="left"></div>
            <div class="center">
              <h1>dfdfd</h1>
            </div>
            <div class="right"></div>
          </article>
       </section>
       //网格布局
           <style>
        html *{
          padding:0;
          margin:0;
        }
        .layout article div{
           min-height:100px;
           display:table-cell
        }
        .layout article{
          display:grid;
          width: 100%;
          grid-template-rows: 100px;
          grid-template-columns: 300px auto 300px;
        }
        .layout.grid .left{
           width:300px;
           background:red;
           width:300px;
        }
        .layout.grid .right{
           background:blue;
        }
        .layout.grid .center{
           background:yellow;
        }
      </style>
       <section class="layout grid">
          <article class="left-right-center">
            <div class="left"></div>
            <div class="center">
              <h1>dfdfd</h1>
            </div>
            <div class="right"></div>
          </article>
       </section>
### 盒模型
#### 基本概念：标准模型+IE模型
### 标准模型和IE模型的区别
### css如何设置这两种模型 
    box-sizing:content-box;
    box-sizing:border-box;
### js如何设置获取获取盒模型对应的宽和高
     dom.style.width/height
     dom.currentStyle.width/height
     window.getComputedStyle(dom).width/height 
     dom.getBoundingClientRect().width/height 
### 实例题（根据盒模型解释边距重叠）
      
### BFC(边距重叠解决方案)
    BFC的基本概念
      块级格式化上下文
    BFC的原理
    BFC的渲染规则
    1BFC的垂直方向上边距不会发生重叠
    2BFC的区域不会于浮动元素发生重叠
    3BFC他是一个独立的容器
    4计算BFC子元素即使float也会参与高度运算 
    如何创建BFC
    1.float值不为none
    2.position值不是static或者relative
    3.display
    4.overflow 
    BFC使用场景
    float布局
    清除浮动 外层包住浮动元素，看不到父元素
    
### DOM事件类
     DOM0 element.onclick=function(){}
     DOM2 element.addEventListener('click',function(){},false)
     DOM3 element.addEventListener('keyup',function(){},false)
#### DOM事件模型
     捕获和冒泡
#### DOM事件流
     捕获到目标到冒泡
#### 描述DOM事件捕获的具体流程
     window->document->html->body->....->目标元素->....->body->html->document->window     
#### Event对象的常见应用
     event.preventDefault()    阻止默认事件
     event.stopPropagation()   阻止冒泡
     event.stopImmediatePropagation() 阻止相同元素的两个click事件阻止一个
     event.currentTarget()     绑定的事件
     event.target()            事件委托 当前点击的元素
#### 自定义事件
     var eve=new Event('custome');事件名
     ev.addEventListener('custome',function(){
       console.log('custome')
     })
     ev.dispatchEvent(eve)
     customEvent都是注册事件 它可以指定参数
     //自己创建一个事件
#### 代码捕获
     var ev=document.getElentById('ev');
     widow.addEventListener('click',function(){
     console.log('window captrue')
     },true);
     document.addEventListener('click',funtion(){ console.log('document captrue')})
     document.documentElement.addEventListener('click',funtion(){ console.log('html captrue')})
     document.body.addEventListener('click',funtion(){ console.log('body captrue')}) 
     ev.addEventListener('click',funtion(){ console.log('ev captrue')},true) 
### http协议类
#### http协议的主要特点
     简单快速 灵活 无连接 无状态 
#### http报文的组成部分
     请求报文
       请求行 http方法
       请求头 key vlaue值
       空行   
       请求体  
     响应报文
       状态行   
       响应头
       空行
       响应体
#### http方法
     GET-> 获取资源
     POST-> 传输资源
     PUT -> 更新资源
     DELETE-> 删除资源
     HEAD-> 获取报文首部  
#### post和get的区别
     GET在浏览器回退是无害的，而POST会再次提交请求
     GET产生的URL地址可一呗收藏，而POST不可以
     GET请求会被浏览器主动缓存，而POST不会，除非手动设置
     GET请求只能进行url编码，而POST支持多种编码方式
     GET请求参数会被完整保留在浏览器历史记录里，而POST中的参数不会被保留
     GET请求在URL中传送的参数是有长度限制的，而POST没有限制
     对参数的数据类型，GET只接受ASCII字符，而POST没有限制
     GET比POST更不按安全，因为参数直接暴露在URL上，所以不能用在传递敏感信息
     GET参数通过URL传递，POST放在Request body中
#### http状态码
     1xx：指示信息-表示请求已接受，继续处理
     2xx：成功-表示请求已被成功接受
     3xx：重定向-要完成请求必须进行更近一步的操作
     4xx：客户端错误-请求有语法错误或请求无法实现
     5xx：服务器错误-服务器未能实现合法的请求 
     200ok: 客户端请求成功
     206 Partial Content：客户发送了一个带有Range头的GET请求，服务器完成了它
     301 Moved Permanently: 所请求的页面已经转移至新的url
     302 FOUND: 所请求的页面已经临时转移至新的url
     304 Not Modified ：客户端有缓冲的文档并发出了一个条件性的请求，服务器告诉客户，原来缓冲的文档还可以继续使用 
     400 Bad request : 客户端请求有语法错误，不能呗服务器所理解
     401 Unauthorized： 请求未授权，这个状态代码必须和WWW-AuthenticateBAO报头域一起使用
     403 Forbidden：对被请求页面的访问被禁止
     404 Not Found : 请求资源不存在
     500 Internal Server Error: 服务器发生不可预期的错误原来缓冲的文档还可以继续使用
     503 Server Unavailable: 请求未完成，服务器临时过载或当机，一段时间后可能恢复正常

#### 什么是持久连接
     HTTP协议采用“请求-应答”，当使用普通模式，既非Keep-Alive模式时，每个请求、应答客户和服务器都要新建一个连接，完成之后立即断开连接（HTTP协议为无连接的协议）
     当使用keep-Alive模式（又称持久连接、连接重用）时，keep-Alive功能使客户端服务端的连接持续有效，当出现对服务器的后继请求时，keep-Alive功能避免了建立或者重新建立请求
#### 什么是管线化
      在使用持久连接的情况下，某个连接上消息的传递类似于
      请求1->响应1->请求2->响应2->请求3->响应3 
      某个连接上的消息变成了类似这样
      请求1->请求2->请求3->响应1->响应2->响应3
      
      管线化机制通过持久连接完成，仅HTTP/1.1支持次技术
      只有GET和HEAD请求可以进行管线化，而post则有所限制
      初次创建连接时不应启动管线机制，因为对方（服务端）不一定支持HTT/1.1版本的协议
      管线化不会影响响应到来的顺序，如上面的例子所示，响应返回的顺序并未改变
      http/1.1要求服务端支持管线化，但并不要求服务器端也对响应进行对于管线化的请求
      管线化处理，只要求不失败即可
      由于上面提到的服务器端问题，开启管线化很可能并不会带来大幅度的性能提升，并且很多服务器和代理程序对管线化的支持并不好，因此现代浏览器如chrome和firefox默认并为开启管线化支持
### 原型链类
#### 创建对象有几种方法
     var o1={name:'o1'}
     var o11=new Object({name:'o11'})
     var M=function(){this.name='o2'}
     var o2=new M();
     var P={name:'o3'}
     var o3=Object.create(p) 
### 原型、构造函数、实例、原型链 
     
#### instanceof的原理
#### new 运算符  
     一个新的对象被创建。它继承自foo.protype构造函数foo被执行。执行的时候，相应的传参会被传入，同时上下文（this）
     会被指定为这个新实例。new foo等同于new foo（），只能用在不传递任何参数的情况如果构造函数反悔了一个“对象”，那么这个
     会取代整个new出来的结果。如果构造函数没有返回对象，那么new出来的结果为步骤1创建的对象 
### 面向对象
#### 类与实例
     类的声明
      function Animal(){
        this.name ='name'
      }
      es6
      class Animal2(){
        constructor(){
           this.name=name; 
        }
      }v
     var new1=new Animal();
     var new2= new Animal() 
#### 类的继承
     如何实现继承
     //借助构造函数实现继承
     function Parent1(){
       this.name="parent1";
     }
     function Child1(){
       Parent.call(this);//apply
       this.type='child1';
     }
     //这种继承方法不能继承父级原型上方法
     //借助原型链实现继承
     funtion Parent2(){
       this.name="parent2
     }
     function child2(){
       this.typ2='child2';
     }
     Child2.prototype=new Parent2();
     //这种方式会让他们公用同一个父级，父级上面的值是引用改变子级的某一个值另一个子级的值也会改变
     //组合方式
     function Parent3(){
       this.name='parent3'
     }
     function Child3(){
        Parent3call(this);
        this.typ2='child3;
     }
      Child3.prototype=new Parent3(); 
      var s3=new Child3();
      var s4=new Child3();
      //组合优化1
      function Parent4 (){
       this.name='parent4'
     }
     function Child4(){
        Parent4.call(this);
        this.typ2='child3;
     }
      Child4.prototype=Parent4.prototype;
      var s3=new Child4();
      var s4=new Child4();
      //这种方式缺点是 父类的构造函数执行了2次  
      //组合优化2
      function Parent4 (){
       this.name='parent4' 
     }
     function Child4(){
        Parent4call(this);
        this.typ2='child3;
     }
      Child4.prototype=Object.create(Parent4.prototype)
      Child4.prototype.constructor=Child4
      var s3=new Child4();
      var s4=new Child4();
     继承的几种方式
### 通信类
#### 什么是同源策略及限制
     同源策略限制从一个源加载的文档或脚本如何与来自另一个源的资源进行交互。
     这是一个用于隔离潜在恶意文件的关键的安全机制
     
     cookie\localStorage和indexDB无法读取
     DOM无法获得
     Ajax请求不能发送
#### 前后端如何通信
     ajax
     websocket
     cors
#### 如何创建ajax
     XMLhttprequest对象的工作流程
     兼容性处理
     事件的触发条件
     事件的触发顺序
     util.json=function(options){
         var opt = {
           url: '',
           type: 'get',
           data:{},
           success:function(){},
           error:function(){}
         }
         util.extend(opt,options);
         if(opt.url){
           var xhr = XMLHttpRequest? new XMLHttpRequest():new window.ActiveXObject('')
           var data = opt.data,
               utl = opt.url,
           type = opt.type.toUpperCase(),
           dataArr=[];
           for(var k in data){
             dataArr.push(k+'='+data[k]);
           }
           if(type==='GET'){
             url = url+'?'+dataArr.join('&');
             xhr.open(type,url.replace(/\?$/g,''),true;
             xhr.send();
           }
           if(type === 'POST'){
             xhr.open(type,url,true);
             xhr.setRequestHeader('Content-type','application/x-www-form-urlencoded');
             xhr.send(dataArr.join('&');
           }
           xhr.onload=function(){
             if(xhr.status===200||xhr.status===304){
               var res;
               if(opt.success&&opt.success instanceof Funtion){
                  res =JSON.parse(res);
                  opt.success.call(xhr,res);
               }
             }else{
               if(opt.error&&opt.error instanceof Function){
                 opt.error.call()xhr.res
               }
             }
           }
         }
      }
#### 跨域通信的几种方式
     JSONP
     Hash
     postMessage
     websocket
     CORS
### 安全类
#### CSRF
     基本概念和缩写
     CSRF,通常称为跨站请求伪造，英文名Cross-site request forgery
     攻击原理
     用户登陆A网站下发cookie，如果B网站引诱你点击A网站某个链接的操作看到cookie就会执行这个操作
     防御措施
     token验证
     referer验证 观看这个链接的来源
     隐藏令牌   和token差不多只不过把数据写在head上
     
#### XSS
     基本概念和缩写
     xss cross-site scripting 跨站脚本攻击
### 渲染机制
#### 什么是DOCTYPE及作用
      DTD（document type definition 文档类型定义）是一系列的语言规则，用来定义xml或html的文档类型。浏览器会使用他来判断文档类型，决定使用何种协议来解析，以及切换浏览器模式
      DOCTYPE是用来声明文档类型和DTD规范的，一个主要的用途便是文件的合法性验证。如果文件代码不合法，那么浏览器便会出一些差错
#### 浏览器渲染过程
      html经过html parser转换成DOM tree ,style sheets->css parser-> style rules,让后DOM tree和style rules相结合
      attachment->render tree但他不能计算元素在哪个位置通过layout完成最后绘画让后显示
      
#### 重排reflow
     定义 DOM结构中的各个元素都是自己的盒子（模型），这些都需要浏览器根据各种样式来计算并根据计算结果将元素放到它该出现的位置，这个过程称之为reflow
     触发reflow
     当你增加、删除、修改DOM结点时，会导致reflow或repaint
     当你移动DOM的位置，或者搞个动画的时候
     当你修改css样式的时候
     当你resize窗口的时候，或是滚动的时候
     当你修改网页的默认字体时
#### 重绘repaint
     定义 当各种盒子的位置、大小以及其他属性，流入颜色、字体大小等都确定下来后，浏览器于是便把这些元素都按照个子的特性绘制了一遍，于是页面的内容出现了，这个过程称之为repaint
     触发repaint
     DOM改动
     css改动
#### 布局layout
### 运行机制类
    console.log(1);
    setTimeout(function(){
     console.log(2);
    },0)
    console.log(3);
    答案是 1 3 2 因为js是单线程 js的运行队列先走同步任务后走异步任务。所以当遇到setTimeout异步任务时先挂起，把后面的同步任务完成最后才走setTimeout
#### 如何理解JS的单线程
     一个时间之内只能执行一个任务
     什么是任务队列
     同步任务和异步任务，异步放入时间和执行时间
     setTimeout(function(){},1000);
     他首先是执行到这个语句先挂起让后等同步任务完成并1000ms到了之后放入异步任务队列执行
     什么是Event Loop
### 页面性能类
#### 题目：提升页面性能的方法有哪些
     资源压缩合并，减少HTTP请求
     非核心代码异步加载->异步加载的方式   1动态加载脚本 2 defer 3 async  ->异步加载的区别 defer是在html解析完之后才会执行，如果是多个，按照加载的顺序一次执行 async是在加载玩之后立即执行，如果是多个，执行顺序和加载顺序无关
     
     利用浏览器缓存->缓存的分类->缓存的原理
     缓存的分类
       强缓存
       EXpires Expires：Thu，21 jan 2017 23：39：02 GMT
       Cache-Control Cache-Control:max-age=3600
       协商缓存
       last-Modified if-Modified-Since last-Modified：web，26 jan 2017 00：35：11 GMT
       Etag if-None-Match
     使用CDN
     预解析DNS
     <meta http-equiv="x-dns-prefetch-control" content="on">
     这个是在https下强制打开a标签链接的与解析因为https下会关闭DNS与解析
     <link rel="dns-prefetch" href="//host_name_to_prefetch.com">
     打开a标签预解析
### 错误监控类
    前端错误的分类
    即使运行错误：代码错误
    资源加载错误
    错误的捕获方式
    try..catch window.onerror
    资源加载错误
    object.onerror perormance.getEntries() error事件捕获
    延申：跨域的js运行错误可以捕获吗。错误提示什么，应该怎么处理
    1、在script标签增加crossorigin
    2、设置js资源响应头Access-Control-Allow-Origin:*;
    
    
    上报错误的原理
    采用ajax通信的方式上报
    利用Image对象上报
    <script>
     (new Image()).src="http://baidu.com/tesjk?r=tksjk"
    </script>
 ### 拿到一个面试题，你第一时间看到的是什么->
 ### 又如何看待网上搜出来的永远也看不完的题海->不变应万变
 ### 如何对待接下来遇到的面试题？->题目到知识再到题目 
 #### js中使用typeof能得到的哪些类型 
      考点：js变量类型
 #### 何时使用=== 何时使用==？
      考点：强制类型转换
 #### window.onload和DOMContentLoaded的区别？
      考点：浏览器渲染过程
 #### 用js创建10个<a>标签,点击的时候弹出来对应的序号
      考点:作用域
 #### 简述如何实现一个模块加载器，实现类似require.js的基本功能
      考点：js模块化
 #### 实现数组的随机排序
      考点：js基础算法
