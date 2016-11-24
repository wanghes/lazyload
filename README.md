# lazyload
全的的图片懒加载整理

###简单的是实现图片懒加载
```javascript
    var imgs = document.getElementsByTagName('img');
    function lazyload(){
        var scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop; // 获取滚动条的偏移量
        var viewportSize = window.innerHeight || document.documentElement.clientHeight || document.body.clientHeight; // 获取视口高度
        for(var i=0; i<imgs.length; i++) {
            var x =scrollTop+viewportSize-imgs[i].offsetTop;
            if(x>0){
                imgs[i].src = imgs[i].getAttribute('data-echo');
            }
        }
    }
    lazyload()
    window.onscroll = function(){
        setInterval(lazyload,300);
    }
```
