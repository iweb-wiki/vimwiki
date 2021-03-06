# Composer 版本约束

## 语义化版本

版本格式：主版本号. 次版本号. 修订号，版本号递增规则如下： 主版本号：当你做了不兼容的 API 修改， 次版本号：当你做了向下兼容的功能性新增， 修订号：当你做了向下兼容的问题修正。 先行版本号及版本编译信息可以加到 “主版本号. 次版本号. 修订号” 的后面，作为延伸。

## 范围

可使用比较操作符指定范围： `>` `>=` `<` `<=` `!=` 

使用空格 ` ` 或者逗号 `,` 表示逻辑与

使用双竖线 `||` 表示逻辑上的或

> 与的优先级大于或

## 不限定版本：*

根据配置中的 `minimum-stability` 的值情况来决定安装最新的 dev 还是 stable 版本

```
"require" : {
    "vendor/package" : "*"
}
```

## 使用 `dev-` 前缀加分支名

使用该分支下最新的提交

```
"require" : {
    "vendor/package" : "dev-master"
}
```

## 使用 `~` 约束符锁定小版本

定义了最小的版本，并且允许版本的最后一位版本号进行升级

```
"require" : {
    "vendor/package1" : "~1.2",
    "vendor/package2" : "~1.2.3"
}
```

`~1.2` 相当于 `>=1.2 <2.0.0`

`~1.2.3` 相当于 `>=1.2.3 <1.3.0`

> `~` 作用在主版本号上，`~1` 会被当作 `~1.0` 对待

## 使用 `^` 约束符锁定大版本

锁定不允许变的第一位

```
"require" : {
    "vendor/package1" : "^1.2.0",
}
```

`^1.2` 相当于 `>=1.2 <1.x.x`

> 如果版本是 `1.0` 以下， `^` 的作用与 `~` 一样。
> `^0.0.3` 表示：`>=0.0.3 <0.0.4`
> **主版本号为零（0.y.z）的软件处于开发初始阶段，一切都可能随时被改变。这样的公共 API 不应该被视为稳定版。**

## 版本稳定性

没有显示指定版本的稳定性，Composer 会根据使用的操作符，默认在内部指定为 `-dav` 或者 `-stable`

| 约束         | 内部约束                   |
| :-:          | :-:                        |
| 1.2.3        | =1.2.3.0-stable            |
| >1.2         | >1.2.0.0-stable            |
| >=1.2        | >=1.2.0.0-dev              |
| >=1.2-stable | >=1.2.0.0-stable           |
| <1.3         | <1.3.0.0-dev               |
| <=1.3        | <=1.3.0.0-stable           |
| 1-2          | >=1.0.0.0-dev <3.0.0.0-dev |
| ~1.3         | >=1.3.0.0-dev <2.0.0.0-dev |
| 1.4.*        | >=1.4.0.0-dev <1.5.0.0-dev |

`minimum-stability` 的值（按照稳定性排序）：`dev`， `alpha`， `beta`， `RC`  和 `stable`

可通过**稳定性标识**来修改默认行为（`@dev`，`@stable`）

## 参考资料

- [关于 Composer 版本约束表达式的使用](https://overtrue.me/articles/2017/08/about-composer-version-constraint.html)
- [你必须知道的 Composer 版本约束](https://laravel-china.org/topics/10807/the-composer-version-of-the-constraint-you-must-know)
