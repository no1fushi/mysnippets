# mysnippts

It is snippets used in vim extension [neosnippet](https://github.com/Shougo/neosnippet.vim)  

## Files
All files are in snippets directory

* java.snip  
  
## Installation
Please install according to each package manager.  
Here we use [neobundle](hhttps://github.com/Shougo/neobundle.vim).  

Write the following in ~/.vimrc  
```
" Plugins
:let g:neobundle_default_git_protocol='https'
if has('vim_starting')
	set runtimepath+=~/.vim/bundle/neobundle.vim/
		if !isdirectory(expand("~/.vim/bundle/neobundle.vim/"))
			echo "install NeoBundle..."
			:call system("git clone https://github.com/Shougo/neobundle.vim ~/.vim/bundle/neobundle.vim")
	endif
endif

call neobundle#begin(expand('~/.vim/bundle/'))

NeoBundleFetch 'Shougo/neobundle.vim'

" snippet
NeoBundle 'Shougo/neosnippet'
NeoBundle 'Shougo/neosnippet-snippets'
NeoBundle 'no1fushi/mysnippets'

"" Setting
if neobundle#is_installed('neosnippet')
	imap <C-k>	<Plug>(neosnippet_expand_or_jump)
	smap <C-k>	<Plug>(neosnippet_expand_or_jump)
	xmap <C-k>	<Plug>(neosnippet_expand_target)
	if has('conceal')
		set conceallevel=2 concealcursor=niv
	endif
	let g:neosnippet#snippets_directory='~/.vim/bundle/neosnippet-snippets/snippets/,~/.vim/bundle/mysnippets/snippets/'
endif
```  

Use [myvimrc](https://github.com/no1fushi/ConfigFile/blob/master/soft/vim/.vimrc)
for troublesome cases  
However, other extensions are also installation and become my specification  
