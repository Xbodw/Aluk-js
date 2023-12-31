# Aluk-js
To view English documents, please go to “README-en.md”


Aluk是一个有些类似于Jquery的库,它的用途也很多,目前是1.4.2版本
在线引用链接:
<http://powernod.com/u/388c1af3a993eff1>
## 基本用法

要使用Aluk来搜索DOM元素,你可以这么做:
```javascript
aluk(你的属性选择器);
```
该操作返回的是一个querylist列表对象,还包括一组aluk独有的函数方法.你可以通过`aluk(你的属性选择器)[第几项]`来访问单个元素,但单个元素无法使用aluk的函数方法.
当然了,aluk也可以像jquery那样,使用html代码或者元素对象:
```javascript
aluk(`<div class='b'></div>`)
```
该操作返回一个未被追加到页面上的querylist列表,你可以通过`aluk(你的属性选择器)[第几项]`来访问单个元素,但单个元素无法使用aluk的函数方法.
或者使用aluk将单个元素转换为aluk的querylist对象:
```javascript
aluk(document.body);
```

## 高级用法

Aluk配套的一组函数和属性是可以使用的.

默认的Aluk语言为英文,我们可以通过`aluk.language = 'zh-cn';`来改变aluk的当前语言,包括错误提示

但是aluk只支持中文和英文两种语言.所以属性值只有`en-us`和`zh-cn`。

 ### Object转Css
你没听错,Aluk是可以将Object类型转换为Css的.
```javascript
var css ='';
aluk.objectToCss({"text-align":"center"，"color":"red"})。forEach(cssl => {css+=cssl;})
```
这样,变量css里的内容就是我们的css了

 ### 对Aluk对象设置css
SetCss用法如下:
```javascript
SetCss(index,cssList)
```
这个index指的是我们aluk对象里的第几项,也就是说我们要对这里面的哪一项进行css修改操作.cssList是css (Object)列表
示例:
```javascript
var rtc = aluk('#rtc');
//以下的第一项使用0来表示,第二项使用1,以此类推
rtc.setCss(0，{"text-align":"center"，"color":"red"}); //对div rtc设置css属性,该操作会返回css的行数.
```
 ### 移动或追加Aluk对象到元素
 用法如下:
 ```javascript
 AppendorMoveto(index,appender)
 ```
 index的含义前面讲过,appender指的是想要把元素移动或追加到哪个元素的子项里
 示例:
 ```javascript
  var rtc = aluk('#rtc');
  //以下的第一项使用0来表示,第二项使用1,以此类推
  rtc.AppendorMoveto(0,document.head);
```
示例里的document.head可以用HTML的Element对象来表示,也可以用aluk的querylist来表示

### 创建HTML元素(多选项)
用法如下:
```javascript
aluk.createElementX(options)
```
options是一个object对象,里面包含了对创建元素的要求
createElementX返回一个Promise对象,其中的PromiseResult就是我们创建的元素.
比如:
```javascript
  var options = {
    "ElementType":"div"， //设置元素类型
    "id":"a"， //设置id,可写可不写,不写把这一行删掉
    "Class":"b"， //设置Class,也是可写可不写,不写把这一行删掉
    "innerHTML":"<a>&nbsp:123</a>"
    }; //设置innerHTML,按需求可以填可以不填,不写把这一行删掉
    
    var element;
    aluk.createElementX(options)。then(res => element=res);
```

### 在控制台上显示图片
我们在1.4.2更新了这个函数,具体用法如下:
```javascript
aluk.ShowConsolePictures(url,options)
```
其中,url可以为网络https或http链接,也可以为base64链接

比如可以这么用:
```javascript
aluk.ShowConsolePictures(`https://file/path/to/png`，{
    size: "1200"，
    height: "600" //百分比,控制台给的空间小,所有必须大于100%
})
```
这样,就能把图片清晰的显示在控制台上

### 转换网络链接为Base64
1.4.2更新
用法:
```javascript
aluk.WebUrlToBase64(url,callback)
```
例如:
```javascript
aluk.WebUrlToBase64('https://path/to/url'，ce => {
	console.log(ce)
	})
```

## 多次搜索
1.4.2更新
用法如下:
```javascript
continue(select)
```
该操作对一个querylist对象使用continue函数,在对象内根据选择器搜索元素并返回一个新的querylist对象
示例:
```javascript
const listdiv = aluk('div');
const lista = listdiv.continue('a[id="b"]')  //根据原来的对象listdiv返回新的querylist对象lista
```

## 全部删除
1.4.2更新
原版的aluk(1.2.1)只能通过forEach函数进行逐次删除,于是我们更新了这个RemoveX函数:
```javascript
RemoveX()
```
具体用法如下
```javascript
const lista = aluk('div')
lista.RemoveX(); //全部删除
```
