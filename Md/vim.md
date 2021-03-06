* [1. spf13](#1)
* [2. 复制到粘贴版本](#2)
* [3. 折叠](#3)
* [4. 输入emoj](#4)
* [5. 输入时间](#5)
* [6. 设置map](#6)
* [7. vimtutor](#7)
* [8. YCM插件python警告](#8)
* [9. chrome的vim插件](#9)
* [10. 修改文件默认用vim打开](#10)
* [11. ctags跳转](#11)
* [12. 多行重复操作](#12)
* [13. buffer操作](#13)
* [14. 中文乱码处理](#14)
* [15. 多窗口操作](#15)
* [16. vundle插件管理](#16)
* [17. mark标记用法](#17)


1. <p id="1">[spf13](https://github.com/spf13/spf13-vim)
</p>

2. <p id="2">复制到系统粘贴板，安装macvim，alias vi=/usr/local/Cellar/macvim/8.1-149_1/MacVim.app/Contents/MacOS/vim
</p>

3. <p id="3">展开folder zE
   zE是去除所有折叠<br>
   zf%折叠当前括号<br>
   zc折叠当前行， zo打开当前<br >
   zM折叠所有,zR展开所有
   </p>

4. <p id="4">输入emoji，输入模式下[C+v]+u+unicode编码 00a9是版权符号©

```
Apple/Command: 2318 ⌘
Alt/Option: 2325 ⌥
Shift: 21E7 ⇧
Enter: 23ce ⏎
Delete: 232B ⌫
ESC: 238B ⎋
Control: 2303 ⌃
Capslock: 21ea ⇪
Tab: 8677 ⇥
```

</p>

5. <p id="5">__输入时间__，输入模式下，[C+r]+=+strftime("%Y/%m/%d")
</p>

6. <p id="6">针对cpp文件设置快捷键map，在这个文件下增加
    /usr/local/Cellar/macvim/8.1-149_1/MacVim.app/Contents/Resources/vim/runtime/ftplugin/cpp.vim

    ```
    nnoremap <C-b>  <Esc>:w<CR>:!g++ -std=c++11 %<CR>
    nnoremap <Leader>b  <Esc>:w<CR>:!g++ -std=c++11 %<CR>

    ```

    设置Leader：

    ```
    let mapleader = ','
    ```

</p>

7. <p id="7">vim自带教程 vimtutor
</p>

8. <p id="8">YouCompleteMe插件python警告的[处理办法]("https://github.com/Valloric/YouCompleteMe/issues/3062")
</p>

9. <p id="9">chrome 的vim插件[vimium]("https://chrome.google.com/webstore/detail/vimium/dbepggeogbaibhgnhhndojpepiihcmeb");
</p>

10. <p id="10">默认打开方式改为vim，使用Automator写一个application，执行下面的AppleScript

```
on run {input}
   set the_path to POSIX path of input
   set cmd to "vim " & quoted form of the_path
   tell application "System Events" to set terminalIsRunning to exists application process "Terminal"
   tell application "Terminal"
      activate
      if terminalIsRunning is true then
         do script with command cmd
      else
         do script with command cmd in window 1
      end if
   end tell
end run

```
</p>

11. <p id="11">ctags跳转</br>
  ctags -R 在根目录下生成ctags文件用于分析</br>
  [CTRL+]]跳转到函数定义，CTRL+t跳回</br>
  CTRL+O光标跳回，CTRL+I光标跳前</br>
  下一个文件:bn，上一个文件:bN</br>
  gd文本匹配，当前文件跳转并且高亮展示</br>
  跨文件跳转到变量定义[+CTRL+i, CTRL+o跳回</br>
</p>

12. <p id="12">多行重复操作</br>
  可视模式选中多行，:之后输入norm! . or norm! @a
</p>

13. <p id="13">多buffer操作

  * 查看buffer， :ls
  * 通过索引跳转， :1b
  * 两个buffer互跳，  Ctrl+^

</p>

14. <p id="14">中文乱码处理</br>

```
set fileencodings=utf-8,gb2312,gb18030,gbk,ucs-bom,cp936,latin1
set enc=utf8
set fencs=utf8,gbk,gb2312,gb18030
```

</p>

15. <p id="15">多窗口操作<br>

>< Ctrl-w > + c关闭当前窗口<br>
> < Ctrl-w > + hjkl选中窗口<br>
> x，最大化Tagbar当前窗口

</p>

16. <p id="16">vundle插件管理

  * :BundleList 列举
  * :BundleInstall 安装所有插件
  * :BundleClean 清除列表中没有的插件

</p>
17. <p id="17">mark标记用法

  * 标记位置ma，mb，mc
  * 跳转到标记'a, 'b, 'c

</p>
