# Highcharts-
### Hihcharts是一个非常流行,界面美观的纯javaScript图表库
## 它主要包括两个部分: Highcharts 和Highstock: 
Highcharts可以为您的网站或Web 应用程序提供直观,互动式图标.目前支持线,样条,面积,areaspline,柱形图,条形图饼图和散点图类型 
Highstock可以为您方便地建立股票或一般的时间轴图表。它包括先进的导航选项，预设的日期范围，日期选择器，滚动和平移等等。

如果想要了解更多Highcharts的信息，可以参考官网：http://www.highcharts.com。

-  这里就不过多阐述怎么来使用了,我们直接进入使用技巧和使用方式跟注意的事项.... 
```javascript
var chart1; // 全局变量
$(document).ready(function() {
      chart1 = new Highcharts.Chart({
         chart: {
            renderTo: 'container',
            type: 'bar'
         },
         title: {
            text: 'Fruit Consumption'
         },
         xAxis: {
            categories: ['Apples', 'Bananas', 'Oranges']
         },
         yAxis: {
            title: {
               text: 'Fruit eaten'
            }
         },
         series: [{
            name: 'Jane',
            data: [1, 0, 4]
         }, {
            name: 'John',
            data: [5, 7, 3]
         }]
      });
   });
```
- 上述代码适用于使用jQuery作为基本框架的情况，$(document).ready()函数，表示在文档加载完成后进行相应处理。如果你使用MooTool等其他JS框架，-  
- 需要使用相对应的代码来替代$(document).ready()函数。
  如果你想生成HighStock图表，有一个单独的构造方法调用Highcharts.StockChart。在这些图表中，数据源是一个典型的JavaScript数组数据。其来源可 
以是一个单独的JavaScript文件，或者是通过Ajax调用远程服务器提供的数据。
```javascript
var chart1; // 全局变量
$(document).ready(function() {
      chart1 = new Highcharts.StockChart({
         chart: {
            renderTo: 'container'
         },
         rangeSelector: {
            selected: 1
         },
         series: [{
            name: 'USD to EUR',
            data: usdtoeur // 数组变量
         }]
      });
   });
```
```HTML
<!--在页面中添加一个DIV元素，作为放置Highcharts图表的容器。需要为其设置ID值，与第2步rendTo参数绑定。设置的宽度和高度将作为Highcharts图表的宽度和高度。-->

<div id="container" style="width: 100%; height: 400px"></div>
```


 1. 在这里我还是建议大家使用一些良好的代码习惯   如: 
  
  ```javascript
  var options = {
  chart:{
        renderTo:'container',
        defaultSeriesType:'bar'
  },
  series:[{
  name:'Jane', data:[1,0,4]}]
  }
  ```
-  在创建命名的对象后,我们可以通过,操作符来扩展其成员.假设我们已经定义了一个对象(见良好的风格代码).下面的代码代码将添加 
-  加另一个series.请记住options.series是一个数组,因此我们可以使用push方法
```javascript
      options.series.push({
      name:''john',data:[3,4,2]})
```
- 另外一个可以排上用场的事实是,对于javaScript对象来说点符号（.）和方括号[]是等价的。所以，你可以通过名称来访问成员。这意味着：
```javascirpt
options.renderTo
```
### 等价于
```javascript
opntions['renderTo']
```
###  更多关于Highcharts 使用可以参考
http://www.cnblogs.com/liuhaorain/archive/2012/01/24/2311352.html
