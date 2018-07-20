1. [spf13](https://github.com/spf13/spf13-vim)
2. 复制到系统粘贴板，安装macvim，alias vi=/usr/local/Cellar/macvim/8.1-149_1/MacVim.app/Contents/MacOS/vim
3. 展开folder zE
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
