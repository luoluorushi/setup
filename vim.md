1. [spf13](https://github.com/spf13/spf13-vim)
2. 复制到系统粘贴板，安装macvim，alias vi=/usr/local/Cellar/macvim/8.1-149_1/MacVim.app/Contents/MacOS/vim
3. 展开folder zE
4. 输入emoji，输入模式下[C+v]+u+unicode编码 00a9是版权符号©
5. 输入时间，输入模式下，[C+r]+=+strftime("%Y/%m/%d")
6. 针对cpp文件设置快捷键map，在这个文件下增加
    /usr/local/Cellar/macvim/8.1-149_1/MacVim.app/Contents/Resources/vim/runtime/ftplugin/cpp.vim
    ```
    nnoremap <C-b>  <Esc>:w<CR>:!g++ -std=c++11 %<CR>

    ```


