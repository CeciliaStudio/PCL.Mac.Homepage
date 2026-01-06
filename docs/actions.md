# 操作

在按钮等控件被点击时，你可能希望给用户一些反馈。我们将这些反馈行为称为“操作（`action`）”。<br>
出于安全性考虑，主页不支持直接执行代码，但你可以在 XML 中声明一系列操作。<br><br>
操作声明格式：<br>

```xml
<操作类型 参数名1="参数值1" 参数名2="参数值2"/>
```

例如：<br>

```xml
<MyButton label="Hello">
    <showHint type="finish" content="Hello, world!"/>
</MyButton>
```

你也可以为同一个控件声明多个操作，点击时会按顺序执行：<br>

```xml
<MyButton label="打开 PCL.Mac.Homepage 的 GitHub 仓库">
    <openUrl url="https://github.com/CeciliaStudio/PCL.Mac.Homepage"/>
    <showHint type="finish" content="执行完成！"/>
</MyButton>
```

其中，`openUrl` 和 `showHint` 是操作类型，`type="finish"` 和 `content=xxx` 是参数。<br><br>
下面是所有可用的操作类型及参数说明：<br>

## openUrl

使用浏览器打开 URL。

### 参数

| 参数名 | 类型    | 描述     | 默认值 |
| ------ | ------- | -------- | ------ |
| url    | 字符串  | 目标 URL | 无     |

## openFile

打开本地文件。

### 参数

| 参数名      | 类型    | 描述                                 | 默认值  |
| ----------- | ------- | ------------------------------------ | ------- |
| path        | 字符串  | 目标文件路径                         | 无      |
| showInParent| 布尔值  | 是否在父文件夹中显示该文件，而不是打开该文件 | false   |

## switchInstance

切换当前实例。

### 参数

| 参数名 | 类型    | 描述               | 默认值 |
| ------ | ------- | ------------------ | ------ |
| id     | 字符串  | 目标实例 ID（约等于实例名） | 无     |

## showHint

显示提示。

### 参数

| 参数名   | 类型                  | 描述     | 默认值 |
| -------- | --------------------- | -------- | ------ |
| content  | 字符串                | 提示文本 | 无     |
| type     | info&#124;finish&#124;critical | 提示类型 | 无     |

## launch

启动游戏。

### 参数

| 参数名  | 类型    | 描述                 | 默认值  |
| ------- | ------- | -------------------- | ------- |
| instance| 字符串  | 实例名               | 无      |
| server  | 字符串  | 游戏启动后加入服务器 | false   |