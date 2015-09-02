# modeljs

当前的mvvm框架虽然解决了vm到view的实时更新，但跟html紧耦合的特性注定了它们无法包容互联网上种类丰富的控件库。
modeljs尝试以另外一种思路解决这个问题。

```javascript
var vm = new absVm({
	name: 'zhanglei',
	age: 30,
	list: [
		{childName: 'child1', childAge: 1},
		{childName: 'child2', childAge: 2},
		{childName: 'child3', childAge: 3},
	],
	salary: 1000,
	yearsalary1: 'this.salary * 12',
	yearsalary2: function (){
		return this.salary * 12;
	}
});
//设置初始化数据json
vm.setModel(dataJson);
//获取数据json
vm.getModel()//dataJson
//监听某字段的变化
vm.watch('list.childName', function (newVal, oldVal){
	
});
vm.watch('list').render('#container .grid');
//设置某字段的名称
vm.set('name', newValue);
vm.set('list[1].childName', newValue);
vm.set('list[1]', {childName: 'child3', childAge: 3});
//实时渲染到某区域
vm.render('#contaner');
vm.render('list', '#contaner .grid', '<ul>{{each list}}{{/each}}</ul>');
```

```兼容vuejs


```