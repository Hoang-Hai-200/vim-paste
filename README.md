<img width="812" height="270" alt="image" src="https://github.com/user-attachments/assets/97e4908d-5212-44ae-aab5-5dc58b16eaac" />
# 🩹 Vim Paste 

A lightweight Vim plugin that lets you enter **Insert mode with `set paste` enabled** — perfect for pasting text without unwanted indentation or autoformatting.

> 💡 *Best used with [vim-airline](https://github.com/vim-airline/vim-airline)* for a clean `[PASTE]` indicator on your statusline.

---

## 📦 Installation

1. With [vim-plug](https://github.com/junegunn/vim-plug), simply add this line to your `.vimrc`:

           Plug 'Hoang-Hai-200/vim-paste'


2. if not copy script to ~/.vimrc or ~/.config/nvim/init.vim

        let g:paste_mode = 0
        
        nnoremap <silent> <leader>i :call StartPasteMode()<CR>
        
        function! StartPasteMode()
            set paste
            let g:paste_mode = 1
            startinsert
        endfunction
        
        autocmd InsertLeave * if g:paste_mode | call StopPasteMode() | endif
        
        function! StopPasteMode()
            set nopaste
            let g:paste_mode = 0
        endfunction

## 🚀 Usage

If you're using **[vim-airline](https://github.com/vim-airline/vim-airline)**, I am recommended to add:

        set noshowmode
<img width="812" height="270" alt="image" style="display:block; margin:auto;"  src="https://github.com/user-attachments/assets/c13dee9c-57c4-4a6c-bdc1-cc6cbdf16d41" />

Press leader + i ( leader commonly \ or , ) to:
        
        ✅ Automatically enter Insert mode
        
        ✅ Set paste option
        
        ✅ Automatically disable paste mode when leaving Insert mode
