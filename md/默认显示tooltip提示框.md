<!--
 * @Author: tangdaoyong
 * @Date: 2021-02-03 13:28:28
 * @LastEditors: tangdaoyong
 * @LastEditTime: 2021-02-03 13:43:38
 * @Description: ECharts 默认显示tooltip提示框
-->
# ECharts 默认显示tooltip提示框

`ECharts`中的`tooltip`提示框默认是鼠标悬浮事件，`echarts`中的`dispatchAction`函数可以默认有触发这个事件，实现开始显示时就显示一个`tooltip`提示框，如果再鼠标悬浮初始时显示的则消失。

1. 先实现`tooltip`中的`formatter`。
```js
var option = {
    tooltip: {
        formatter: function(params) {
            var html = '<p style="margin-bottom: 4px;font-weight:bold; color: #666">' + params[0].name + '</p>';
            return html;
        }
    }
};        
```

**注意**只展示了相关的部分代码。

2. 使用`option`初始化`Echarts`。
```js
var lineBar = echarts.init(document.getElementById('chart'));
lineBar.setOption(option);
```

现在`Echarts`渲染的视图就具有了鼠标悬浮时显示`tooltip`提示框。

3. 设置默认显示的`tooltip`提示框。

```js
lineBar.dispatchAction({
    type: 'showTip',
    seriesIndex: 1,  // 显示第几个series
    dataIndex: chartData.xAxis.length - 1 // 显示第几个数据
});
```

**注意**`dataIndex`与`xAxis`或`yAxis`数据对应，如上是`x`轴的最后一条数据。