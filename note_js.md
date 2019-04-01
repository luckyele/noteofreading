在一个js文件中建立模块：


hello.js

'''
'use strict'

var s = 'hello';

function greet(name) {
	console.log(s + ',' + name + '!');
}

module.exports = greet;
'''

这是将greet作为模块暴露出去，其他模块就可以使用greet函数。


main.js
'''
'use strict'

//引入greet函数
var greet = require('./hello');

var s = 'Lister';

greet(s);
'''

这里若写成require('hello')，表示Node依次在内置模块、全局模块和当前模块查找hello.js。

这种模块加载机制被称为CommonJS规范，每个.js文件都是一个模块，其内部变量名、函数名互不冲突。也可以用这种机制暴露变量。

Node.js使用闭包，将全局变量变成函数内部变量。


在Node环境中，从一个模块中输出变量的方法有二种：
1 对module.exports赋值 module.exports = {hello:hello}
2 直接使用exports   exports.hello = hello;

如果输出的是一个函数或数组，只能用第一种方式。第一方式通用好。


通用模块：fs 

## 异步读文件 
'''
'use strict'

var fs = require('fs')

fs.readFile('sample.txt', 'utf-8', function (err, data) {
	if (err) {
		console.log(err);
	} else {
		consolo.log(data);
	}
		
});
'''

// Buffer -> String
var text = data.toString('utf-8');
console.log(text);

// String -> Buffer
var buf = Buffer.from(text, 'utf-8');
console.log(buf);

## write files

fs.writeFile('output.txt', data, function (err) {
	if (err) {
		console.log(err);
	} else {
		console.log('ok.');
	}
});


## http server 
'''
var http = require('http');

var server = http.createServer(function (request, response) {
	console.log(request.method + ':' + request.url);
	response.writeHead(200, {'Content-Type':'text/html'});
	response.end('<h1>Hello world!</h1>');
		
});

server.listen(8080);
console.log('Server is running at http://127.0.0.1:8080/');
'''
