# lazyload
全的的图片懒加载整理

###简单的是实现图片懒加载
**加载的html**
```html
<div><img src="echojs/images/placeholder.png" width="220" height="220" data-echo="http://pic.mousebird.cn/images/57d0bcbcNd22cad97.png"></div>
<div><img src="echojs/images/placeholder.png" width="220" height="220" data-echo="http://pic.mousebird.cn/images/57de9c90N48e3c482.jpg"></div>
<div><img src="echojs/images/placeholder.png" width="220" height="220" data-echo="http://pic.mousebird.cn/images/555af01aN0bf1fcb1.jpg"></div>
<div><img src="echojs/images/placeholder.png" width="220" height="220" data-echo="http://pic.mousebird.cn/images/572b0233N573b593b.jpg"></div>
<div><img src="echojs/images/placeholder.png" width="220" height="220" data-echo="http://pic.mousebird.cn/images/572f631fNee6ec9db.jpg"></div>
<div><img src="echojs/images/placeholder.png" width="220" height="220" data-echo="http://pic.mousebird.cn/images/576a30a9N6e0daf1e.jpg"></div>
<div><img src="echojs/images/placeholder.png" width="220" height="220" data-echo="http://pic.mousebird.cn/images/57057f7eN936fd6c0.jpg"></div>
<div><img src="echojs/images/placeholder.png" width="220" height="220" data-echo="http://pic.mousebird.cn/images/562898c4N3e135baf.jpg"></div>
<div><img src="echojs/images/placeholder.png" width="220" height="220" data-echo="http://pic.mousebird.cn/images/573357c1N10bb6e16.jpg"></div>
<div><img src="echojs/images/placeholder.png" width="220" height="220" data-echo="http://pic.mousebird.cn/images/57612849N9e40d33b.jpg"></div>
```
**加载的javascript**
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
