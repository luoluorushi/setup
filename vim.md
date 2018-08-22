1. [spf13](https://github.com/spf13/spf13-vim)
2. 复制到系统粘贴板，安装macvim，alias vi=/usr/local/Cellar/macvim/8.1-149_1/MacVim.app/Contents/MacOS/vim
3. 展开folder zE
   zE是去除所有折叠，展开用zR，折叠用zM，打开当前折叠zO
4. 输入emoji，输入模式下[C+v]+u+unicode编码 00a9是版权符号©
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
5. 输入时间，输入模式下，[C+r]+=+strftime("%Y/%m/%d")
6. 针对cpp文件设置快捷键map，在这个文件下增加
    /usr/local/Cellar/macvim/8.1-149_1/MacVim.app/Contents/Resources/vim/runtime/ftplugin/cpp.vim
    ```
    nnoremap <C-b>  <Esc>:w<CR>:!g++ -std=c++11 %<CR>
    nnoremap <Leader>b  <Esc>:w<CR>:!g++ -std=c++11 %<CR>

    ```
    设置Leader：
    ```
    let mapleader = ','
    ```
7. vim自带教程 vimtutor

8. YouCompleteMe插件python警告的[处理办法]("https://github.com/Valloric/YouCompleteMe/issues/3062")
9. chrome 的vim插件[vimium]("https://chrome.google.com/webstore/detail/vimium/dbepggeogbaibhgnhhndojpepiihcmeb");
10. 默认打开方式改为vim，使用Automator写一个application，执行下面的AppleScript
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
11. ctags跳转
  ctags -R 在根目录下生成ctags文件用于分析</br>
  [CTRL+]]跳转到函数定义，CTRL+t跳回</br>
  CTRL+O光标跳回，CTRL+I光标跳前</br>
  下一个文件:bn，上一个文件:bN</br>
  gd文本匹配，当前文件跳转并且高亮展示</br>
  跨文件跳转到变量定义[+CTRL+i, CTRL+o跳回</br>
