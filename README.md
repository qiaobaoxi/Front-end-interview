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
    
     
