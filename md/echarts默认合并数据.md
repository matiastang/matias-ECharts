<!--
 * @Author: tangdaoyong
 * @Date: 2021-07-07 17:26:01
 * @LastEditors: tangdaoyong
 * @LastEditTime: 2021-07-07 17:27:20
 * @Description: echarts默认合并数据
-->
# echarts默认合并数据

ReactEcharts组件会默认将原渲染图表的数据和二次渲染图表的数据默认合并，
即在图表某些变量改变时二次渲染echarts图表，如果本次渲染少了之前的参数，会一并把之前参数的数值合并到图表

## 处理

发现<ReactEcharts />组件不仅具有option和style的属性，

还有notMerge和LazyUpdate属性————

notMerge————可选，是否不跟之前设置的 option 进行合并，默认为 false，即合并
LazyUpdate————可选，在设置完 option 后是否不立即更新图表，默认为 false，即立即更新

在这里我给<ReactEcharts />组件中加入notMerge={true}即可实现图表每次更新不再合并之前数据

myChart.setOption(option);

setOption有3个属性，setOption(option,notMerge,lazyUpdate);