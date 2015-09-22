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
 
    import urllib.request,os,hashlib; h = 'eb2297e1a458f27d836c04bb0cbaf282' + 'd0e7a3098092775ccb37ca9d6b2e4b7d'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)       

* 接下来可以`command+shift+p`输入install找到`Package Control install`选项，输入则安装软件，输入`remove`则可以删除软件。  

* 必备的插件:  

1. Alignment  \\等号对齐    
2. ConvertToUTF8 && Codecs33 \\支持中文utf8  
3. Docblockr  \\注释插件，写完代码后，在行首加入\\*，回车后自动生成注释  
4. Tomorrow color  \\神配色，我一直用    

* MarkDown插件  
单独列出来，是因为我找到一个新的插件，感觉比较好用。  
一直不用sublime写markdown，主要是因为无法即时预览，这点不如Mou，但是有了一个神插件就破了这点，让markdown也可以即时预览了，听我慢慢道来.  

1. MarkdownEditing  
>这是必装的，否则没有好看的背景，就没有了写作的动力。  

~~2. Markmon  real-time markdown perview  
就是这个插件，可以让所见即所得，先来一张官网上的图~~  
![](https://packagecontrol.io/readmes/img/11c350617e7bdfe32be854f8f77239678ecfb54a.gif)  

~~[有关介绍](https://packagecontrol.io/packages/Markmon%20real-time%20markdown%20preview)  ~~

~~先在SublimeText3中安装Markmon插件~~ 

~~其次在OSX系统中安装markmon~~  

`npm install -g markmon`  

~~需要nodejs环境支持~~  

`brew install node`  

~~最后在安装用于格式转换的软件pandoc~~  
[下载地址](https://github.com/jgm/pandoc/releases/download/1.13.2/pandoc-1.13.2-osx.pkg)  

~~简单设置一下:~~  

｀Preferences > Package Settings > markmon > Settings - User｀   

~~设置以下样式: ~~ 

    {
    //On Windows try "markmon.cmd" if you get errors.
    //If markmon is not on your path you'll need to use a full path to it
    "executable": "markmon",
    "port": 3002,
    "command": "pandoc -t HTML5 --mathjax",
    "stylesheet": null,
    "projectdir": null
    }   

~~其次在`Preferences → Package Settings → Markmon → Key Bindings - Default`这里可以绑定快捷键。~~

    [
        { "keys": ["ctrl+super+m"], "command": "markmon_toggle", "args":
            {
                "enable": true
            }
        }
    ]
   

~~3.还可以再安装Markdown Preview来预览自己写的markdown。 ~~ 

4.之前安装的Markmon插件，虽然可以正常使用，但是需要机器上安装markmon、node、还要有pandoc等等。我发现一个不用安装很多东西的插件，再来记录一次，因为我改成这个新的插件了。  

###安装：  
1. 通过Package Control来安装OmniMarkupPrevewer。  

2. 简单的设置：  


```js
    /* OmniMarkupPreviewer default setting, DO NOT MODIFY */
    {
    "server_host": "127.0.0.1",
    "server_port": 51004,
    "refresh_on_modified": true,
    // delay after modified, in milliseconds
    "refresh_on_modified_delay": 500,
    "refresh_on_saved": true,

    // User defined command for launching preview in web browser
    // For example:
    //   Launching preview using Google Chrome in OS X:
    //      ["open", "-a", "Google Chrome", "{url}"]
    "browser_command": ["open", "-a", "Google Chrome", "{url}"],

    // User public static files should be placed into
    //   ${packages}/User/OmniMarkupPreviewer/public/
    // User templates should be placed into:
    //   ${packages}/User/OmniMarkupPreviewer/templates/
    // Requires browser reload
    // Built-in templates: github, github-v1
    "html_template_name": "github",

    // Polling interval for content changes in web browsers, in milliseconds
    // Requires browser reload
    "ajax_polling_interval": 500,

    // list of renderers to be ignored, case sensitive.
    // Valid renderers are: "CreoleRenderer", "MarkdownRenderer", "PodRenderer",
    //     "RDocRenderer", "RstRenderer", "TextitleRenderer"
    // for example, to disable Textile and Pod renderer:
    //   "ignored_renderers": ["TextitleRenderer", "PodRenderer"]
    "ignored_renderers": [""],

    // Enable MathJax (http://www.mathjax.org/)
    // MathJax javascript libraries will downloaded automatically, it may take some while.
    // When MathJax is properly installed into OmniMarkupPreviewer/public/mathjax, you
    //   have to reload your browser to get mathjax work.
    // KNOWN ISSUES:
    //   * It may be slow base on your computer/browser performance, so you may want to
    //     tune the following options:
    //         "ajax_polling_interval", "refresh_on_modified" and "refresh_on_modified_delay"
    "mathjax_enabled": false,

    // Custom options for exporting
    "export_options" : {
        // follow "html_template_name" rules
        // Built-in templates: github-export, github-v1-export
        "template_name": "github-export",
        // ".":  export to the same folder as markup file.
        // null: export to system temp folder.
        // NOTE: folder shall exist, or it will fallback to system temp folder.
        "target_folder": ".",
        // format string for filename timestamp
        "timestamp_format" : "_%y%m%d%H%M%S",
        "copy_to_clipboard": false,
        // Open with default browser or whatever customized in "browser_command".
        "open_after_exporting": false
    },

    // MarkdownRenderer options
    "renderer_options-MarkdownRenderer": {
        // Valid extensions:
        // - OFFICIAL (Python Markdown) -
        //   "extra": Combines ["abbr", "attr_list", "def_list", "fenced_code", "footnotes", "tables", "smart_strong"]
        //            For PHP Markdown Extra(http://michelf.ca/projects/php-markdown/extra/)
        //   "abbr": http://packages.python.org/Markdown/extensions/abbreviations.html
        //   "attr_list": http://packages.python.org/Markdown/extensions/attr_list.html
        //   "def_list": http://packages.python.org/Markdown/extensions/definition_lists.html
        //   "fenced_code": http://packages.python.org/Markdown/extensions/fenced_code_blocks.html
        //   "footnotes": http://packages.python.org/Markdown/extensions/footnotes.html
        //   "tables": http://packages.python.org/Markdown/extensions/tables.html
        //   "smart_strong": http://packages.python.org/Markdown/extensions/smart_strong.html
        //   "codehilite": http://packages.python.org/Markdown/extensions/code_hilite.html
        //   "meta": http://packages.python.org/Markdown/extensions/meta_data.html
        //   "toc": http://packages.python.org/Markdown/extensions/toc.html
        //   "nl2br": http://packages.python.org/Markdown/extensions/nl2br.html
        // - 3RD PARTY -
        //   "strikeout": Strikeout extension syntax - `This ~~is deleted text.~~`
        //   "subscript": Subscript extension syntax - `This is water: H~2~O`
        //   "superscript": Superscript extension syntax 0 `2^10^ = 1024`
        //   "smarty" or "smartypants": Python-Markdown extension using smartypants to emit
        //                   typographically nicer ("curly") quotes, proper
        //                   ("em" and "en") dashes, etc.
        //                   See: http://daringfireball.net/projects/smartypants/
        //                   And: https://github.com/waylan/Python-Markdown/blob/master/docs/extensions/smarty.txt
        "extensions": ["extra","toc","smarty","superscript","tables", "strikeout", "fenced_code", "codehilite"]
    }
}
```
###关于配置的解释  

    "server_host": "127.0.0.1",   

开启预览服务的ip地址。如果设置成本机的内网地址，则可以享受到用ipad或者类似工具预览的效果。   
    `“browser_command": ["open", "-a", "Google Chrome", "{url}"], `  

默认是用safari打开，这段命令使用了Chrom来打开预览的网页。  

    `"ignored_renderers": [""]`  

说明中写到，这里有很多支持的标记语言，虽然我不清楚是什么，但是都打开了，如果想关闭某种，就写到[]里面。  

    `"extensions": ["extra","toc","smarty","superscript","tables", "strikeout", "fenced_code", "codehilite"]`  

这里的渲染扩展，可以查看上面的说明选择关闭或者开启。  

2. sftp  

command+shift+p出现搜索框，输入install package，输入sftp可以找到sftp插件  

安装好后，执行File -> SFTP/FTP -> Setup Server来生成配置文件  

保存后，点击菜单File -> SFTP/FTP -> Browse Server来连接远程服务器。  

注意端口为22，路径需要使用绝对路径：  

    "remote_path": "/home/name/"  

> Setup Server生成的配置文件，应该放在菜单Preferences > Browse Packages...下的User/sftp_servers目录中。
 
附上万能注册码，设置Setting - User中:  

```  
{
    "email" : "xiaosong@xiaosong.me",
    "sftp"  :  "d419f6-de89e9-0aae59-2acea1-07f92a"
}
``` 


未解决的问题：  

1. Markmon通过pandoc转换md到html5以后，显示的并不好看，比如\<code>就处理的不是markdown的原版，或许是我的问题，我再找找答案。  
2. OmniMarkupPreviewer预览的网页无法跟着ST3的界面滚动，也许是我设置的问题？








