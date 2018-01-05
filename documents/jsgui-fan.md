# JS规范

页面中书写到js时请务必参考本规范 Javascript是控制用户与页面交互、前端与后台数据交互的重要工具，在我们的日常工作中应用非常广泛。为了有效提高代码的质量，基于“易维护、易调试、高性能”的原则，参考业界知名团队的规范与指南制订本规范，大家在编写JavaScript代码时，应尽量遵守本规范，提高自己的代码质量。

## 1、命名

Javascript是区分大小写的语言，在对Javascript种的变量、函数、常量等命名时，应该遵循Javascript自身采用的命名规则，以保持代码的一致性。具体规则如下：

### 常量:

Javascript自身不支持常量，在程序中如果要定义“禁止定义后改变”的变量，可以参考其他编程语言，采用下划线分隔的全大写字符串来定义。例如：PAGEBASECOLOR、COOKIR\_PREFIX等。

### 变量:

首字母小写，驼峰命名法，原则上采用名词及名词短语，描述该变量代表的数据。例如：videoId、userLevel、linkToHome、btnDown、totalPages

### 函数:

首字母小写、驼峰命名法，原则上函数采用动词及动词短语，以描述该函数的行为，对象采用名词及名词词组。例如：login\(\)、checkLogin\(\)、showVideo\(\)、switchTabs\(\)、changeLevel\(\)、addClass\(\)、loadScript\(\)

### 类及命名空间:

首字母大写、驼峰命名法。例如：LoginManager、Dialog、LazyLoader、FlashManager

### 文件名:

全小写、单词间可以不分隔或用连接线"-"分隔，文件名可以加.min/.debug表示文件状态，例如：common.js（一般的文件名）、milo.min.js\(压缩后的文件\)、common.debug.js\(未压缩、调试用的文件\)。

### 可读性:

在未做压缩处理的源代码中，类、变量、函数的命名应该尽量具有语义，应当避免“a”、“b”、“yy”这类无意义的命名（循环语句中的i/j/k等习惯用法除外）。代码的压缩，应该采用专门的工具（如YUI Compressor、Google Closure）来进行，不要人为用无意义的命名来减少代码量。

## 2、变量的定义和初始化

Javascript并不强调变量在使用前必须定义。但是如果没有使用var关键字来定义变量，则该变量将会成为全局变量。有可能会造成对同名全局变量的覆盖，在多人协作开发、引入多个库或多个js文件的情况下，容易导致变量名冲突等问题。因此，对变量的定义和初始化建议参照以下规则： 总是将代码包裹成一个 IIFE\(Immediately-Invoked Function Expression\)，用以创建独立隔绝的定义域。这一举措可防止全局命名空间被污染。IIFE 还可确保你的代码不会轻易被其它全局命名空间里的代码所修改（i.e. 第三方库，window 引用，被覆盖的未定义的关键字等等）。

#### 不推荐：

```js
var x = 10,
    y = 100;

// Declaring variables in the global scope is resulting in global scope pollution. All variables declared like this
// will be stored in the window object. This is very unclean and needs to be avoided.
console.log(window.x + ' ' + window.y);
```

#### 推荐：

```js
// We declare a IIFE and pass parameters into the function that we will use from the global space
(function(log, w, undefined){
  'use strict';

  var x = 10,
      y = 100;

  // Will output 'true true'
  log((w.x === undefined) + ' ' + (w.y === undefined));

}(window.console.log, window));
```

虽然Javascript是一门弱类型语言，变量的数据类型可以随时自由转换，但是在实际使用中，依然建议大家避免用同一个变量存储不同类型的数据。 在定义变量的同时对其初始化是很好的编程实践，这可以避免后续忘记给变量赋值而直接使用它引发的"undefined"错误。

## 3、代码格式

### 大括号

前大括号始终位于当前行末尾，后大括号新起一行并与代码块的首行保持相同缩进对齐，数组和对象的快速定义可以例外。例如 \_数组和对象的快速定义:

```js
var arr = [1, 2, 3];
var obj = {a: 1, b: 2, c: 3};
```

\_数组初始化:

```js
this.rows_ = [
  '"Slartibartfast" ',
  '"Zaphod Beeblebrox" ',
  '"Ford Prefect" ',
  '"Arthur Dent" ',
  '"Marvin the Paranoid Android" ',
  'the.mice@magrathea.com'
];
```

\_函数调用中:

```js
tvp.play('u1134234422','mod_player', {
  autoplay: '1',
  width: 600,
  height: 449,
  controls: '1'
});
```

\_函数定义:

```js
function functionName() {
    // function codes
}
```

\_代码块:

```js
if (condition == true) {
    // do something
} else {
    // do something else
}

for(var i = 0; i < data.length; i++) {
    // loop body
}
```

```js
/* 不推荐 */
if(event.target)
    return event.target;
else
    return event.srcElement;

/* 推荐 */
if(event.target) {
    return event.target;
} else {
    return event.srcElement;
}
```

`注：对于代码块，始终用大括号包裹，对于单行判断、while循环等可以省略大括号的，一律不省略。`

\#\#\#引号 在处理字符串时，优先使用单引号，仅在必须的情况下才使用双引号。这不仅能保持代码的一致性、缩小代码文件大小，在创建包含HTML代码的字符串时，这尤其有利，例如：

```js
var msg = '<li class="msg">这是一条信息</li>';
```

### 分号

所有的语句必须用分号结尾所有的代码块不得使用分号结尾

```js
/* 不推荐 */

// 例1.
MyClass.prototype.myMethod = function() {
  return 42;
}  // 缺少分号

(function() {
  // some code
})();

// 例2.
var x = {
  'i': 1,
  'j': 2
}  // 缺少分号

[normalVersion, ffVersion][isIE]();

// 例3.
var THINGS_TO_EAT = [apples, oysters, sprayOnCheese]  // 缺少分号.

-1 == resultOfOperation() || die();
```

`这样写会造成什么后果？`

例1：JavaScript 错误 - 首先，原本是定义一个返回42的函数，变成了立即执行，并且把第二个函数当成了调用第一个函数的参数，然后42这个数字被当成一个函数返回并被调用，引发了错误。 例2：你最有可能看到的是代码执行的时候报“no such property in undefined”的错误，因为它会尝试执行x\[ffVersion\]isIE，而x\[ffVersion\]是未定义的。 例3：函数die\(\)只有在resultOfOperation\(\)的结果不为数字的时候才会被执行（预期是不为-1就执行），而THINGSTOEAT则被赋值为die\(\)的执行结果（原本应该是个数组）。

`为什么会这样呢？`

JavaScript要求语句以分号结束，除非解析器可以安全地分析出语句在哪里结束（例如定义函数时结尾的大括号）。在上面的错误范例中，由于函数定义、对象或数组被用在了语句当中，于是结束括号并不足以标识出语句的结尾。于是当下一个标识符可以作为语句的中间部分时（比如例子的中前括号、前中括号、-1等）JavaScript解析器就不会在我们预期的地方结束语句。 因此，不要试图依赖JavaScript解析器来为你“断句”，务必在需要结束语句的地方使用分号明确指出该语句已经结束。

```js
/* 推荐 */

var foo = function() {
  return true;
};  // 正确的结束分号.

function foo() {
  return true;
}  // 这里不要加分号.

if (condition) {
    // do something.
}  // 这里不要加分号

milo.addEvent(g('domId'), 'click', function(){
    // do something
}); // 正确的结束分号

(function(){
    function clickHandler(hotTag) {
        pgvSendClick({hottag:hotTag});
    }  // 这里不要分号
    var btn = document.getElementById('btnDown');
    btnDown.innerHTML = '下载';
    btnDown.click = function() {
      clickHandler('index.btnDown.client.xf');
    };  // 正确的结束分号
})();  // 正确的结束分号
```



