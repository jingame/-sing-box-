## sing-box的结构（Structure）：


```
{
  "type": "",
  "tag": "",
  "format": "",

  ... // Typed Fields
}
```
type是类型，`必需`  , `local`或者`remote`.   
> 在sing-box的分流规则里必须要的  
> local是`指通常指的是用户设备上的本地设置或功能，与通过远程服务器进行的网络活动相对`。  
> remote是`指常指的是远程服务器或服务`
---
<br>

tag是标签，`必需`。  **方便规则集的标签** .

---
<br>

format是格式， '必需'， **规则集的格式**， `source`和`binary`。  
source是`指软件的源服务器或数据源`  
>这通常是指用户的网络请求首先连接到的服务器，它作为中继点将请求转发到最终目的地  

binary是`指软件的可执行文件`。  
> 在计算机编程和软件开发中，"binary" 指的是编译后的程序，它是以二进制格式存储的，可以直接在计算机或移动设备上运行。

---
<br>


## sing-box的局部结构(Local Structure)  

```
{
  "type": "local",

  ...

  "path": ""
}
```
path是路径。`必需`，**规则集的文件路径**     


---
<br>


## sing-box的远程结构(Remote Structure)

```
{
  "type": "remote",

  ...,

  "url": "",
  "download_detour": "",
  "update_interval": ""
}
```

url是指网址，`必需`，**规则集的下载URL**  

---

download_detour是指下载绕行，**下载规则集的出站标签，如果为空，将使用默认出站**。  

---
update_interval是指更新间隔， **规则集的更新间隔。 1d 如果为空则将被使用**  
>1d是表示1天







