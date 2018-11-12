# PHP 小技巧

- `foreach` 效率更高，尽量用 `foreach` 代替 `while` 和 `for` 循环
- 循环内部不要声明变量，尤其是对象这样的变量
- 循环里别用函数
- 在多重嵌套循环中，如有可能，应当将最长的循环放在内层，最短循环放在外层，从而减少 cpu 跨循环层的次数，优化程序性能
- 用单引号替代双引号引用字符串以实现 PHP 性能优化
- 用 `i+=1` 代替 `i=i+1`。符合 c/c++ 的习惯，效率还高
- 优化 Select SQL 语句，在可能的情况下尽量少的进行 `Insert`、`Update` 操作，达到 PHP 性能优化的目的
- 某些地方使用 `isset` 代替 `strlen`
- 尽量的少进行文件操作，虽然 PHP 的文件操作效率也不低的
- 尽可能的使用 PHP 内部函数
- 在可以用 PHP 内部字符串操作函数的情况下，不要用正则表达式
- 在可以用 `file_get_contents` 替代 `file`、`fopen`、`feof`、`fgets` 等系列方法的情况下，尽量用 `file_get_contents`，因为它的效率高得多。但是要注意 `file_get_contents` 在打开一个 URL 文件时候的 PHP 版本问题
- 不要随便就复制变量
- Apache 解析一个 PHP 脚本的时间要比解析一个静态 HTML 页面慢 2 至 10 倍。尽量多用静态 HTML 页面，少用脚本
- 试着喜欢使用三元运算符`(?:)`
- 使用选择分支语句，`switch case` 好于使用多个 `if`，`else if` 语句，并且代码更加容易阅读和维护
- 当 `echo` 字符串时用逗号代替点连接符更快些。`echo` 一种可以把多个字符串当作参数的 “函数”。`echo` 是语言结构，不是真正的函数，故把函数加上了双引号
- 去除 HTML 标签以及空格换行等字符 `preg_replace("/(\s|\ \;|　|\xc2\xa0)/", "", strip_tags($str))`
- 目录分隔符 `DIRECTORY_SEPARATOR`
- 多路径分隔符 `PATH_SEPARATOR`
- `bool || die()`