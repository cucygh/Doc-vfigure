title: 标准折线图 - 折线(面积)图
---

### 标准折线图<a name=stdBar></a>
- [效果图](#effect)
- [安装方式](#install)
- [使用配置](#config)
- [使用方式](#use)
- [样式支持](#style)

效果图：<a name="effect"></a> [回到顶部](#stdBar)
<iframe src="http://fex.dev.quhuhu.com/guohui.yin/v-figure/html/polyline.html" frameborder="0" width="810" height="350"></iframe>
安装方式：<a name="install"></a> [回到顶部](#stdBar)
``` javascript
    var bar=require('lib/polyline/stdPolyLine.js');
```

使用配置：<a name="config"></a> [回到顶部](#stdBar)
``` javascript
    var config={
        id: 'canvas',//画布的id
        width: 800,//画布的宽度
        height: 300,//画布的高度
        title: {
            text: '折线图基本案例',
            subText: '测试用例',
            padding: [-30, -35],
            style: {
                text: {
                    'font-size': 16,
                    fill: '#ab0',
                    'text-anchor': 'start'
                },
                subText: {
                    fill: '#999',
                    'text-anchor': 'start'
                }
            }
        },
        //横坐标显示的内容
        xAxis: ['2001', '2002', '2003', '2004', '2005', '2006', '2007', '2008', '2009', '2010'],
        // 数据列表，支持多维度，每一项是一个维度
        series: [{
            data: [52, -71, 10, 20, 80, 120, 10, 34, 23, 11],
            style: {
                line: {
                    // 描边
                    stroke: '#1ba9ba',
                    'stroke-dasharray': '.',
                    'stroke-width':2,
                    // 圆角
                    r: 5
                },
                point: {
                    stroke: '#1ba9ba',
                    r: 2,
                    fill: '#1ba9ba'
                }
            },
            legend: '测试案例'
        }, {
            data: [42, 90, 20, 10, 551, 20, 100, 64, 43, 11],
            style: {
                line: {
                    // 描边
                    stroke: '#f00',
                    // 圆角
                    r: 4
                },
                point: {
                    stroke: '#f00',
                    r: 0,
                    fill: '#f00'
                }
            },
            legend: '测试案例'
        }],
        // 纵坐标刻度分布，如果没有设置选项，会按多维度的数据自动计算刻度
        yAxis: [10, 30, 50, 60, 90, 200],
        // 动画效果设置
        animation: {
            duration: 1000,//动画时间
            type: 'bounce',//动画类型
            inOut: 500,//回调动画时间
            open: true//是否开启动画
        },
        // 坐标系的样式
        strokeAxis: {
            stroke: '#eee',
            'stroke-linejoin': 'round',
            'stroke-width': 1.5
        },
        // 坐标系的刻度样式
        strokeTick: {
            stroke: '#fff',
            'stroke-linejoin': 'round',
            'stroke-width': 1
        },
        strokeFocus: {
            stroke: '#1ba9ba',
            'stroke-linejoin': 'round',
            'stroke-width': 1.5
        }
    };
```

使用方式：<a name="use"></a> [回到顶部](#stdBar)
``` html
    <div id="canvas"></div>
```

``` javascript
    var r=new bar(config);
    r.render();
```

样式支持：<a name="style"></a> [回到顶部](#stdBar)
``` json
    fill : ['color', 'gradient','image'] //可以是颜色、渐变、图片
    fill-opacity : number   //透明度，要求是数值
    font : string  //字体，和css设置一样
    font-family : string  //字体类型
    font-size : number //字号大小，要求是数值，单位是px
    font-weight: number //字体粗细，要求是数值，单位是px
    opacity : number //透明度
    stroke : string //描边
    stroke-dasharray : string 可选范围：[“”, “-”, “.”, “-.”, “-..”, “. ”, “- ”, “--”, “- .”, “--.”, “--..”]
    stroke-linecap : string 可选范围：[“butt”, “square”, “round”]
    stroke-linejoin: string 可选范围：[“bevel”, “round”, “miter”]
    stroke-opacity : number 描边透明度
    stroke-width : number 描边宽度，默认是1px
    text : string  元素的文本内容，用\n换行
    text-anchor: string 文本对齐方式，可选范围：[“start”, “middle”, “end”]，默认是 middle
```
