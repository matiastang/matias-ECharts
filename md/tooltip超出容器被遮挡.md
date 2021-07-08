<!--
 * @Author: tangdaoyong
 * @Date: 2021-07-08 09:32:12
 * @LastEditors: tangdaoyong
 * @LastEditTime: 2021-07-08 09:35:16
 * @Description: tooltip超出容器被遮挡
-->
# tooltip超出容器被遮挡

当tooltip内容比较多时，导致tooltip超出容器，且被周围的其他dom所遮挡。网上找了一圈发现很多朋友说配置其中的confine: true, 然而该配置只是将tooltip限制在该容器内。

## tooltip.confine

是否将tooltip框限制在图表的区域内

## tooltip.extraCssText

tooltip有一个extraCssText属性，顾名思义为额外的css，这不就完事了吗！ 添加一个z-index为最大值，解决！

**注意**： 如果使用了transform属性，记得修改translateZ。