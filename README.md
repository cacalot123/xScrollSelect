# xScrollSelect
模拟仿移动端iOS滚动选择的js插件

## 安装
* 引入iscroll-probe.js
* 引入xScrollSelect.js
* 引入xScrollSelect.css

## 使用示例
```javascript

var xs = new xScrollSelect({
    spaceNum: 2, //预留的格子数, 即选择空白区域所占的格子数, 默认为2
    itemWidth: 40, //每个格子的宽度单位px，默认为40
    showCover: true, //是否展示背景遮罩,
    probeType: 2, //iscroll配置参数，表示scroll监听中切换active的class的检查灵敏度，取值1，2，3越高越灵敏，默认为2
    //需要展示的数据, name是展示名称，其他数据可以放入每个{}，回调时会把选中的数据原样返回
    items: [
    	{name: '第一个'},
    	{name: '第二个'},
    	{name: '第三个', id: 200},
    	{name: '第四个'}
    ],
    onScrollEnd: function(params) {
      /*回调方法当用户选择停止时触发
      params返回格式 
       {
          index: 0,
          data: {
            name: '第三个',
            id: 200
          }
       }
      */
    },
    onConfirm: function(params) {
    	//回调方法当前用户按确认按钮时候触发,params同onScrollEnd中的格式
    }
});

//实例方法
//展示
xs.show();
//隐藏
xs.hide();

```

## demo
![demo show](https://github.com/zhang-xiao/xScrollSelect/blob/master/xScrollSelect.gif)


