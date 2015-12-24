title: 标准条形图 - 柱状(条形)图
---

### 标准条形图<a name=stdBar></a>
- [效果图](#effect)
- [安装方式](#install)
- [使用配置](#config)
- [使用方式](#use)
- [样式支持](#style)

效果图：<a name="effect"></a> [回到顶部](#stdBar)
<iframe src="http://fex.dev.quhuhu.com/guohui.yin/v-figure/html/stripBar.html" frameborder="0" width="810" height="350"></iframe>

安装方式：<a name="install"></a> [回到顶部](#stdBar)
``` javascript
    var bar=require('lib/bar/stripBar.js');
```

使用配置：<a name="config"></a> [回到顶部](#stdBar)
``` javascript
    var config={
        id: 'canvas',//画布的id
        width: 800,//画布的宽度
        height: 300,//画布的高度
        title: {
            text: '柱状图基本案例',//画布的主标题
            subText: '测试用例',//画布的副标题
            padding: [-30, -35],//标题的位置偏移量，第一个是上偏移、第二个是左偏移
            //style是标题的样式设置，见[样式支持]
            style: {
                text: {
                    'font-size': 16,//字号大小
                    fill: '#ab0',//字体颜色
                    'text-anchor': 'start'//字体对齐方式：左对齐
                },
                subText: {
                    fill: '#999',
                    'text-anchor': 'start'
                }
            }
        },
        //纵坐标显示的内容
        yAxis: ['巴西', '中国', '印度', '尼泊尔', '英格兰'],
        // 数据列表，支持多维度，每一项是一个维度
        series: [{
            //数据
            data: [102, 10, 10, 20],
            //样式
            style: {
                // 填充色
                fill: '#1ba9ba',
                // 描边
                stroke: '#fff',
                // 圆角
                r: 2
            },
            // 图例文案
            legend: '测试案例'
        }, {
            data: [20, 12, 34, 23],
            style: {
                fill: '#f00',
                stroke: '#fff',
                r: 2
            },
            legend: '二维码'
        }, {
            data: [40, 62, 84, 123],
            style: {
                fill: '#f45',
                stroke: '#fff',
                r: 2
            },
            legend: '健身房'
        }, {
            data: [30, 92, 4, 163],
            style: {
                fill: '#d05',
                stroke: '#fff',
                r: 2
            },
            legend: '思考'
        }, {
            data: [10, 192, 14, 63],
            style: {
                fill: '#a45',
                stroke: '#fff',
                r: 2
            },
            legend: '数据库'
        }],
        // 动画效果设置
        animation: {
            duration: 1000,//动画时间
            type: 'bounce',//动画类型
            inOut: 500,//回调动画时间
            open: true//是否开启动画
        },
        reverse: true//坐标系是否反转，默认为false
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
