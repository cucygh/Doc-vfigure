title: 自定义折线图 - 折线(面积)图
---

### 自定义折线图<a name=stdBar></a>
- [效果图](#effect)
- [安装方式](#install)
- [使用配置](#config)
- [使用方式](#use)
- [样式支持](#style)

效果图：<a name="effect"></a> [回到顶部](#stdBar)
<iframe src="http://fex.dev.quhuhu.com/guohui.yin/v-figure/html/polylineMobile.html" frameborder="0" width="810" height="350"></iframe>
安装方式：<a name="install"></a> [回到顶部](#stdBar)
``` javascript
    var bar=require('lib/polyline/stdPolyLine.js');
```

使用配置：<a name="config"></a> [回到顶部](#stdBar)
``` javascript
    var c1 = {
        id: 'canvas',
        padding:'50 30 50 0',
        series: [{
            data: [52, 70, 10, 20, 80, 120, 10, 34, 23, 11],
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
            data: [42, 90, 20, 10, 70, 20, 100, 64, 43, 11],
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
        xAxis: ['2001', '2002', '2003', '2004', '2005', '2006', '2007', '2008', '2009', '2010'],
        animation: {
            line: {
                speed: 500,
                type: '<>'
            },
            point: {
                speed: 200,
                type: '<>'
            }
        },
        isxAxis: true,
        isyAxis: false,
        isGrid: true,
        isTitle: false,
        isLegend: false,
        isFocus: true,
        isZebra: true,
        isData: true
    };
    var c2 = {
        id: 'yAxis',
        padding:'50 0 50 30',
        series: [{
            data: [52, 70, 10, 20, 80, 120, 10, 34, 23, 11],
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
            data: [42, 90, 20, 10, 70, 20, 100, 64, 43, 11],
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
        xAxis: ['2001', '2002', '2003', '2004', '2005', '2006', '2007', '2008', '2009', '2010'],
        animation: {
            line: {
                speed: 500,
                type: '<>'
            },
            point: {
                speed: 200,
                type: '<>'
            }
        },
        isxAxis: false,
        isyAxis: true,
        isGrid: false,
        isTitle: false,
        isLegend: false,
        isFocus: false,
        isZebra: false,
        isData: false
    };
```

使用方式：<a name="use"></a> [回到顶部](#stdBar)
``` html
    <article class="flexbox">
        <nav class="flex left" id="yAxis"></nav>
        <section class="flex right" id="canvas"></section>
    </article>
```
``` css
    *{
        padding: 0;
        margin: 0;
    }
    .flexbox {
        display: flex;
    }
    .flex {
        flex: 1;
    }
    .left {
        flex: none;
        width: 30px;
    }
    .right {
        overflow-x: auto;
    }
```

``` javascript
    var m = new stdPolyLine(c1);
    var y = new stdPolyLine(c2);
    m.render();
    y.render();
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
