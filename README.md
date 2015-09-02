# modeljs

当前的mvvm框架都跟html层紧耦合，这种特性注定了它们无法以开放的姿态包容目前丰富的控件库。modeljs尝试以另外一种思路解决这个问题。

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
vm.set(dataJson);
//获取数据json
vm.get()//dataJson
//监听某字段的变化
vm.watch('list.childName', function (newVal, oldVal){
	
});
//设置某字段的名称
vm.set('name', newValue);
vm.set('list[1].childName', newValue);
vm.set('list[1]', {childName: 'child3', childAge: 3});
//实时渲染到某区域
vm.render('#contaner');
vm.render('list', #contaner .grid', '<ul>{{each list}}{{/each}}</ul>');
```
