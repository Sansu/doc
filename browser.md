常见浏览器兼容问题总结
===
##表现方式：
* uc 8.0以下浏览器，样式加载错乱
* 解决方法：联系uc将自己网站的域名和相关信息提供给uc，将网站加入uc的白名单。
---
##css兼容性问题：
* Pad对fixed的支持不好，尽量不要使用，如果必须要用一定不能有可输入的input在上面；
* 不要在滚动的div里面直接加absolute的元素，会闪烁；
* div直接滚动不流畅，需要-webkit-overflow-scrolling:touch；
* Retina屏幕需要使用两倍图片；
* 两个相同背景颜色的div，滚动时会产生黑色背景
* 安卓部分手机400电话无法自动转接
---
##性能
######1、楼盘图片异步加载，根据设备分辨率不同切割不同的图片尺寸
```javascript
    function lazyLoad(){
        function replaceImg(v) {
                var w = parseInt(v.getStyle("width")),h = parseInt(v.getStyle("height"));
                if (window.devicePixelRatio && window.devicePixelRatio!=1) {
                    w = parseInt(w*window.devicePixelRatio);
                    h = parseInt(h*window.devicePixelRatio);
                }
                size = w+'x'+h;
                if(w && h)s = s.replace(re,w+'x'+h);
        }
        function lazyOnpos(){

        };
        J.g(d).on('scroll',function(){
            
        });
        document.addEventListener("touchmove",function(event){
            
        },false);
    }
```
######2、在头部引入基本js类库和css，在页面渲染之后再引入页面依赖js
######3、图片合并
---

##手机物理返回键无法执行js
```javascript
window.addEventListener('popstate',function);
```

    