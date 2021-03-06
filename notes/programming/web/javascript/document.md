# JavaScript - Document

## `document.querySelectorAll()`

返回当前文档中匹配一个特定选择器的所有的元素(使用深度优先，前序遍历规则这样的规则遍历所有文档节点) .返回的对象类型是 NodeList

```javascript
elementList = document.querySelectorAll(selectors);
```

> 在Chrome浏览器中可以用`$$()`

## `document.querySelector()`

返回当前文档中匹配一个特定选择器的第一个元素

```javascript
element = document.querySelector(selectors);
```

## `document.cookie`

获取和设置与当前文档相关联的 cookie

**获取所有 cookie**

```javascript
allCookies = document.cookie;
```

**写一个新 cookie**

```javascript
document.cookie = updatedCookie;
```

`updatedCookie` 是一个键值对形式的字符串。注意，你只能用这个方法一次设置或更新一个 cookie。

以下可选的 cookie 属性值跟在键值对后，定义 cookie 的设定/更新，跟着一个分号以作分隔：
* `;path=*path*` (例如 '/', '/mydir') 如果没有定义，默认为当前文档位置的路径。
* `;domain=*domain*` (例如 'example.com'， '.example.com' (包括所有子域名), 'subdomain.example.com') 如果没有定义，默认为当前文档位置的路径的域名部分。
* `;max-age=*max-age-in-seconds*` (例如一年为 60*60*24 * 365)
* `;expires=*date-in-GMTString-format*` 如果没有定义，cookie 会在对话结束时过期这个值的格式参见 `Date.toUTCString()`
* `;secure` (cookie 只通过 https 协议传输)
