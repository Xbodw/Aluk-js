#Aluk-js
To view Chinese documents, please go to "READMEmd"
Aluk is a library that is somewhat similar to Jquery and has many uses. Currently, it is version 1.2.1
##Basic usage
To use Aluk to search for DOM elements, you can do this:
```JavaScript
Aluk (your attribute selector);
```
This operation returns a querylist list object, including a set of unique function methods of aluk. You can access a single element through 'aluk (your attribute selector) [item number]', but a single element cannot use the function methods of aluk
Of course, aluk can also use HTML code or element objects like jquery:
```JavaScript
Aluk (<div class='b '></div>)
```
This operation returns a querylist list that has not been appended to the page. You can access a single element through 'aluk (your attribute selector) [item number]', but a single element cannot use the function method of aluk
Alternatively, use aluk to convert individual elements into aluk's querylist object:
```JavaScript
Aluk (document. body);
```
##Advanced usage
Aluk comes with a set of functions and attributes that can be used
The default Aluk language is English, and we can use 'aluk. language=' zh cn '` To change the current language of aluk, including error prompts
But aluk only supports Chinese and English languages, so the attribute values are only 'en us' and' zh cn '
###Object to Css
Aluk can convert object Type conversion to Css
```JavaScript
Var css='';
Aluk.objectToCss ({"text align": "center", "color": "red"}). forEach (cssl=>{css+=cssl;})
```
So, the content in the variable CSS is our CSS
###Set CSS for Aluk objects
The usage of SetCss is as follows:
```JavaScript
SetCss (index, cssList)
```
This index refers to the number of items in our aluk object, which means which item we need to perform CSS modification operations on. cssList is the CSS (Object) list
Example:
```JavaScript
Var rtc=aluk('#rtc');
//The first item below is represented by 0, the second item is represented by 1, and so on
rtc.setCss (0, {"text align": "center", "color": "red"})// Set the CSS attribute on div rtc, which returns the number of rows in CSS
```
###Move or append Aluk objects to elements
The usage is as follows:
```JavaScript
AppendorMoveto (index, appender)
```
As mentioned earlier, the meaning of index refers to the subitem of which element you want to move or append an element to
Example:
```JavaScript
Var rtc=aluk ('# rtc');
//The first item below is represented by 0, the second item is represented by 1, and so on
Rtc. AppendorMoveto (0, document. head);
```
The document. head in the example can be represented by HTML Element objects or aluk's querylist
###Create HTML element (multiple options)
The usage is as follows:
```JavaScript
Aluk.createElementX (options)
```
Options is an object object that contains the requirements for creating elements
CreateElementX returns a Promise object, where the PromiseResult is the element we created
For example:
  ```javascript
  var options = {
    "ElementType":"div", //设置元素类型
    "id":"a", //设置id,可写可不写,不写把这一行删掉
    "Class":"b", //设置Class,也是可写可不写,不写把这一行删掉
    "innerHTML":"<a>&nbsp:123</a>"
    }; //设置innerHTML,按需求可以填可以不填,不写把这一行删掉
    
    var element;
    aluk.createElementX(options).then(res => element=res);
    ```

