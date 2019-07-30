# WishWall
祝愿墙，可以点击卡片查看，或者删除


### 编程语言 
Javascript、JSON、HTML+CSS

### 功能
1、每次刷新界面，卡片位置重新组合，并根据不同的权值互相重叠

2、点击卡片，最下面的卡片权值变最大，重叠在其他卡片之上

3、双击或点击“关闭”图标，卡片可消失

### 关键代码
        //循环生成div标签，然后为innerHTML属性添加内容
        for(var i=0;i<messages.length;i++){
            //生成新标签
            var newDiv = document.createElement("div");
            //绑定类名和ID
            newDiv.className = "tip1";
            newDiv.id = "tip"+messages[i].id;
            //改变位置
            var topValue = parseInt(Math.random()*400);
            var leftValue = parseInt(Math.random()*700);
            newDiv.style.top = topValue+"px";
            newDiv.style.left = leftValue+"px";
            //赋值内容
            newDiv.innerHTML = '<div class="tip_h" title="双击关闭纸条">'+
                                        '<div class="num">第[49568]条 '+messages[i].time+'</div>'+
                                        '<div class="close" title="关闭纸条" >×</div>'+
                                        '<div class="clr"></div>'+
                                '</div>'+
                                '<div class="tip_c">'+
                                    messages[i].content+
                                 '</div>'+
                                '<div class="tip_f">'+
                                    '<div class="icon">'+
                                    '<img src="images/bpic_1.gif" alt="" title="">'+
                                '</div>'+
                                '<div class="name">'+messages[i].name+'</div>'+
                                    '<div class="clr"></div>'+
                                '</div>';
            //把新创建的元素放入content里面
            content.appendChild(newDiv);


            //绑定事件，提高层级
            newDiv.onclick = fn;

        var index = 1;
        function fn(){
            this.style.zIndex = index;
            index++;
        }

