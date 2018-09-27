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
