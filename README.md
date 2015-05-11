# Sublime Text3

在这里记录一下自己的Sublime Text3的配置，一些参考网上，一些自己找的。  

环境：Yosemite 10.10   

我要求的功能很简单，python以及markdown，然后就是好看。  

####安装Sublime Text3  

官方地址：
[SublimiText3](http://www.sublimetext.com/)

####配置  
关于如何配置SublimeText3，不但官网上网上有很多，而且见仁见智，我现在没做过什么配置，以后有了再补充  

####插件  
* 首先安装的是Package Control  
在SublimeText3里面按键盘的control+\`，然后输入： 

``` 
import urllib.request,os,hashlib; h = 'eb2297e1a458f27d836c04bb0cbaf282' + 'd0e7a3098092775ccb37ca9d6b2e4b7d'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)  

```      

* 接下来可以`command+shift+p`输入install找到`Package Control install`选项，输入则安装软件，输入`remove`则可以删除软件。  

* 必备的插件:  

1. Alignment  \\等号对齐    
2. ConvertToUTF8 && Codecs33 \\支持中文utf8  
3. Docblockr  \\注释插件，写完代码后，在行首加入\\*，回车后自动生成注释  
4. Tomorrow color  \\神配色，我一直用  
5. 


* MarkDown插件  
单独列出来，是因为我找到一个新的插件，感觉比较好用。  
一直不用sublime写markdown，主要是因为无法即时预览，这点不如Mou，但是有了一个神插件就破了这点，让markdown也可以即时预览了，听我慢慢道来.  

1. MarkdownEditing  
>这是必装的，否则没有好看的背景，就没有了写作的动力。  

2. Markmon  real-time markdown perview  
就是这个插件，可以让所见即所得，先来一张官网上的图  
![](https://packagecontrol.io/readmes/img/11c350617e7bdfe32be854f8f77239678ecfb54a.gif)  

[有关介绍](https://packagecontrol.io/packages/Markmon%20real-time%20markdown%20preview)  

先在SublimeText3中安装Markmon插件 

其次在OSX系统中安装markmon  

`npm install -g markmon`  

需要nodejs环境支持  

`brew install node`  

最后在安装用于格式转换的软件pandoc  
[下载地址](https://github.com/jgm/pandoc/releases/download/1.13.2/pandoc-1.13.2-osx.pkg)  

简单设置一下:  

｀Preferences > Package Settings > markmon > Settings - User｀  
设置以下样式:  

```
{
    //On Windows try "markmon.cmd" if you get errors.
    //If markmon is not on your path you'll need to use a full path to it
    "executable": "markmon",
    "port": 3002,
    "command": "pandoc -t HTML5 --mathjax",
    "stylesheet": null,
    "projectdir": null
}```    

其次在`Preferences → Package Settings → Markmon → Key Bindings - Default`这里可以绑定快捷键。

```
[
    { "keys": ["ctrl+super+m"], "command": "markmon_toggle", "args":
        {
            "enable": true
        }
    }
]
```   

3. 还可以再安装Markdown Preview来预览自己写的markdown。  

未解决的问题：  

1. Markmon通过pandoc转换md到html5以后，显示的并不好看，比如\<code>就处理的不是markdown的原版，或许是我的问题，我再找找答案








