# 正则表达式小记

- `\` 一般用于转义字符
- `[]` 字符类定义
- `|` 开始一个可选分支
- `()` 子组
- `-` 标记字符范围

## 常用的元字符

- `.` 匹配除换行符以外的任意字符
- `\w` 匹配字母或数字或下划线或汉字
- `\s` 匹配任意的空白符
- `\d` 匹配数字
- `\b` 匹配单词的开始或结束
- `^` 匹配字符串的开始
- `$` 匹配字符串的结束

## 常用的限定符

- `*` 重复零次或更多次
- `+` 重复一次或更多次
- `?` 重复零次或一次
- `{n}` 重复 n 次
- `{n,}` 重复 n 次或更多次
- `{n,m}` 重复 n 到 m 次

## 常用的反义代码

- `\W` 匹配任意不是字母，数字，下划线，汉字的字符
- `\S` 匹配任意不是空白符的字符
- `\D` 匹配任意非数字的字符
- `\B` 匹配不是单词开头或结束的位置
- `[^x]` 匹配除了 x 以外的任意字符
- `[^aeiou]` 匹配除了 aeiou 这几个字母以外的任意字符

## 常用分组语法

### 捕获

- `(exp)` 匹配 exp，并捕获文本到自动命名的组里
- `(?<name>exp)` 匹配 exp，并捕获文本到名称为 name 的组里，也可以写成 (?'name'exp)
- `(?:exp)` 匹配 exp，不捕获匹配的文本，也不给此分组分配组号

### 零宽断言

- `(?=exp)` 匹配 exp 前面的位置
- `(?<=exp)` 匹配 exp 后面的位置
- `(?!exp)` 匹配后面跟的不是 exp 的位置
- `(?<!exp)` 匹配前面不是 exp 的位置

### 注释

- `(?#comment)` 这种类型的分组不对正则表达式的处理产生任何影响，用于提供注释让人阅读

## 懒惰限定符

- `*?` 重复任意次，但尽可能少重复
- `+?` 重复 1 次或更多次，但尽可能少重复
- `??` 重复 0 次或 1 次，但尽可能少重复
- `{n,m}?` 重复 n 到 m 次，但尽可能少重复
- `{n,}?` 重复 n 次以上，但尽可能少重复

## 模式修饰符

- `U` 默认情况下为贪婪匹配（`u` 匹配结果存在歧义时取长），如果设置了这个修饰符，模式就会成为懒惰匹配（匹配结果存在歧义的取其短）
- `i` 如果设置了这个修饰符，模式中的字母会进行大小写不敏感匹配
- `m` 默认情况下，PCRE 认为目标字符串是由单选字符组成的（然而实际上它可能会包含多行），“行首” 元字符 `(^)` 仅匹配字符串的开始位置，而 “行末” 元字符 `($)` 仅匹配字符串末尾，或者最后的换行符（除非设置了 `D` 修饰符）。这个行为和 prel 相同。当这个修饰符设置之后，“行首” 和 “行末” 就会匹配目标字符串中任意换行符之前或之后，另外，还分别匹配目标字符串的最开始和最末尾位置。这等同于 prel 的 `/m` 修饰符。如果目标字符串中没有 "`\n`" 字符，或者模式中没有出现 `^` 或 `$` ，设置这个修饰符不产生任何影响。
- `s` 如果设置了这个修饰符，模式中的点号元字符匹配所有字符，包含换行符。如果没有这个修饰符，点号不匹配换行符。这个修饰符等同于 perl 中的 `/s` 修饰符。一个取反字符类比如 `[^a]` 总是匹配换行符，而不依赖于这个修饰符的设置。
- `x` 如果设置了这个修饰符，模式中的没有经过转义的或不在字符类中的空白数据字符总会被忽略，并且位于一个未转义的字符类外部的 `#` 字符和下一个换行符之间的字符也被忽略。这个修饰符等同于 perl 中的 `/x` 修饰符，使被编译模式中可以包含注释。注意：这仅用于数据字符。空白字符还是不能在模式的特殊字符序列中出现。

