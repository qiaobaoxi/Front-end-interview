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
