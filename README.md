Smuggler
========

  Python module for converting javascript files to glyph like sequences that run in the browser . Based on [Article](http://patriciopalladino.com/blog/2012/08/09/non-alphanumeric-javascript.html) from Patricio Palladino . 
  
 ## Example :
  
 __input file:__
```javascript
(function(n){
    console.log(n*n);
})(5);
```

__output file:__
```javascript
eval('('+((!!+[]+"")[+[]])+((!+[]+"")[(+!![])+(+!![])])+((+!![]/+[]+"")[+!![]])+((({})+"")[(+!![])+(+!![])+(+!![])+(+!![])+(+!![])])+((!+[]+"")[+[]])+((+!![]/+[]+"")[(+!![])+(+!![])+(+!![])])+((({})+"")[+!![]])+((+!![]/+[]+"")[+!![]])+'('+((+!![]/+[]+"")[+!![]])+')'+'{'+((({})+"")[(+!![])+(+!![])+(+!![])+(+!![])+(+!![])])+((({})+"")[+!![]])+((+!![]/+[]+"")[+!![]])+((!!+[]+"")[(+!![])+(+!![])+(+!![])])+((({})+"")[+!![]])+((!!+[]+"")[(+!![])+(+!![])])+((!!+[]+"")[(+!![])+(+!![])+(+!![])+(+!![])])+'.'+((!!+[]+"")[(+!![])+(+!![])])+((({})+"")[+!![]])+"\x67"+'('+((+!![]/+[]+"")[+!![]])+'*'+((+!![]/+[]+"")[+!![]])+')'+';'+'}'+')'+'('+((+!![])+(+!![])+(+!![])+(+!![])+(+!![]))+')'+';');
```

## Use :

__Requirements__:

I am using [slimit](https://pypi.python.org/pypi/slimit) module to parse javascript input , make sure it is installed  `pip install slimit`

__Standalone:__

Script expects only 1 argument, _File_ or _Directory_ , in the second case all _.js_ files inside _Directory_ and it's parents will be converted .

__As Module:__

From python repl: 
```python
>>> import smuggler
>>> print smuggler.convert_str('console.log("hi");',True)
eval(((({})+"")[(+!![])+(+!![])+(+!![])+(+!![])+(+!![])])+((({})+"")[+!![]])+((+!![]/+[]+"")[+!![]])+((!!+[]+"")[(+!!
[])+(+!![])+(+!![])])+((({})+"")[+!![]])+((!!+[]+"")[(+!![])+(+!![])])+((!!+[]+"")[(+!![])+(+!![])+(+!![])+(+!![])])+
'.'+((!!+[]+"")[(+!![])+(+!![])])+((({})+"")[+!![]])+"\x67"+'('+'"'+"\x68"+((+!![]/+[]+"")[(+!![])+(+!![])+(+!![])])+
'"'+')'+';');
>>> 
```

Now paste the following inside your browser console session .
