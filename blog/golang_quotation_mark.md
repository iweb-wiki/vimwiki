# Golang 双引号、单引号、反引号

## 双引号

表示为 `String`，实质是一个 `byte` 类型的数组，支持转义

## 单引号

表示特殊类型：`rune`，码点字面量，不做任何转义的原始内容

## 反引号

多行原生的 `String` 字面量