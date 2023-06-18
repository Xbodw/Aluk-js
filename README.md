#Aluk-js
To view English documents, please go to "README en. md"
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
Var r
