* 把任何 JavaScript 对象变成 JSON，就是把这个对象序列化成一个 JSON 格式的字符串，这样才能够通过网络传递给其他计算机。
* 花括号表示对象(字典)，方括号表示数组(列表)
* 数组中可以包含多个对象，对象中可以包含多个键/值对
* **json使用场景**：JSON经常应用到的场景是：在后台应用程序中将响应数据封装成JSON格式，传到前台页面之后，需要将JSON格式转换为JavaScript对象，然后在网页中使用该数据。
* 数组是有序的，对象是无序的
* 数字类型的值不能使用引号包裹
* 数组是有序的**值**序列，其中的值可以是对象，也可以是普通的数字类型
* 键名必须是字符串，值可以是任意合法的json值
* `null`可以用在条件判断中，表示为`false`


可以使用 JavaScript 来创建 json 对象：
``` javascript
// 方式1
var jsonobj = {};
// 方式2
var jsonobj = new Object();
// 方式3
var jsonobj = {"name":"tanjuntao", "birth":"19970612"};
```


访问 json 对象中的值
``` javascript
var jsonobj = {"name":"tanjuntao", "birth":"19970612"};
// 方式1：通过`.`运算符
var val = jsonobj.name;
// 方式2：通过方括号`[]`
var val = jsonobj["name"];
```

使用循环访问对象中的所有键
``` javascript
var jsonobj = {"name":"tanjuntao", "birth":"19970612"};
for (x in jsonobj) {
    document.getElementById("demo").innerHTML += x + "<br>";
}
```
使用循环访问对象中的所有值
``` javascript
var jsonobj = {"name":"tanjuntao", "birth":"19970612"};
for (x in jsonobj) {
    document.getElementById("demo").innerHTML += jsonobj[x] + "<br>";
}
```

将 JavaScript 对象装换为文本
``` javascript
String txt = jsonobj.toJSONString();
```
更重要的是，可以将任何 JavaScript 对象转换为 JSON 文本。并非只能处理原来用 JSON 字符串赋值的变量。为了对名为 myObject 的对象进行转换，只需执行相同形式的命令：
``` javascript
String txt = myjsObj.toJSONString();
```

`for-in循环结构`
* 对于数组来说
``` javascript
// data is array
// i is index begin with 0
for (var i in data) {
    ...
}
```

* 对于对象来说
``` javascript
// data is object
// i is the properties of data
for (var i in data) {
    ...
}
```
* example
``` javascript
var data = [
    {"name":"a", "age":12},
    {"name":"b", "age":11},
    {"name":"c", "age":13},
    {"name":"d", "age":16}
];

for (var o in data) {
    // console.log(o);
    // console.log(data[o]);
    console.log(data[o].name + "->" + data[o].age);
}


var data = {
    "name":"juntao",
    "age":111,
    "home":"anqing anhui",
    "brothers": [
        {
           "name":"xiaojun",
           "age":25
        },
        {
            "name":"tanjun",
            "age":28
        }
    ]
};

for (var o in data) {
    // console.log(o);
    // console.log(data[o]);
}

console.log(data["brothers"]);
console.log(data.brothers[1]);
```
