            ####### ####### #     # ####### ####### ######        # 
               #    #        #   #     #    #     # #     #       # 
               #    #         # #      #    #     # #     #       # 
               #    #####      #       #    #     # ######        # 
               #    #         # #      #    #     # #     # #     # 
               #    #        #   #     #    #     # #     # #     # 
               #    ####### #     #    #    ####### ######   #####  
                                                                    
        #     #    #    ######  #    # ######  ####### #     # #     # 
        ##   ##   # #   #     # #   #  #     # #     # #  #  # ##    # 
        # # # #  #   #  #     # #  #   #     # #     # #  #  # # #   # 
        #  #  # #     # ######  ###    #     # #     # #  #  # #  #  # 
        #     # ####### #   #   #  #   #     # #     # #  #  # #   # # 
        #     # #     # #    #  #   #  #     # #     # #  #  # #    ## 
        #     # #     # #     # #    # ######  #######  ## ##  #     # 
                                                                       
                                                                    

Table of Contents
=================


<!-- vim-markdown-toc GFM -->

* [Introduction](#introduction)
* [Headers](#headers)
* [Code Blocks](#code-blocks)
  * [Code Block Text Objects](#code-block-text-objects)
  * [Code Block Movement](#code-block-movement)
* [Text Blocks](#text-blocks)
  * [Text Text Objects](#text-text-objects)
  * [Text Movement](#text-movement)
* [Dependencies](#dependencies)
* [License](#license)

<!-- vim-markdown-toc -->

Introduction
============

Textobj-Markdown provides text objects and movements for markdown and Rmarkdown
files. Textobj-Markdown is built upon, and requires [textobj-user][1]. It
provides default key mappings and movements for code blocks, text between code
blocks, and three levels of headers. If you choose not to apply the default
mappings, simply include the following in you vimrc/init.vim:

```vim
" remove default mappings
let g:__textobj_markdown_no_mappings=1
```

Headers
=======

Textobj-Markdown provides convenient mappings for moving between different levels
of headers. Textobj-Markdown uderstand both styles of headers (i.e. #/## or
===/---). The plug and default mappings are shown below.

```vim
" level 1 headers
" # Header
" or
" Header
" =====
]] "next
[[ "previous

"level 2 headers
" ## Sub Header
" or
" Sub Header
" ----------
][ "next
[] "previous

" level 3 headers
" ### Sub Sub Header
]} "next
[{ "previous
```

Code Blocks
===========

Code Block Text Objects
-----------------------

Textobj-Markdown provides text objects and movement maps for working with code
blocks. There are two sets of mappings for working with code blocks. By default
the are mapped to `if/af` and `iF/aF`. When on or inside of a current code block,
both of these mappings work on the current block. When outside of a code block
the `if/af` mappings will search forward for a code block and the `iF/aF` mappings
will search backward for a code block.

```vim
" current or next code block

" inside of block plug
<plug>(textobj-markdown-chunk-i)
" inside of block default
if
  
"around block plug
<plug>(textobj-markdown-chunk-a)
"around block default
af

" current or previous code block

" inside of block plug
<plug>(textobj-markdown-Bchunk-i)
" inside of block default
iF

"around block plug
<plug>(textobj-markdown-Bchunk-a)
"around block default
aF
```

Code Block Movement
-------------------

In addition to text objects, Textobj-Markdown also provides movement mappings
for code blocks.

```vim
" start of code block
]f " next
[f " previous

" end of code block
]g " next
[g " previous
```

Text Blocks
===========

Text Text Objects
-----------------

```vim
" current or next text block
im " inside of block
am " around block

" current or previous text block
iM " inside of block
aM " around block
```

Text Movement
-------------

```vim
" start of text block
]m " next
[m " previous

" end of text block
]n " next
[n " previous
```

Dependencies
============

[textobj-user][1]

License
=======

Copyright (c) Torsten Schmits. Distributed under the terms of the [MIT
License][2].

[1]: https://github.com/kana/vim-textobj-user 'textobj-user'
[2]: http://opensource.org/licenses/MIT 'mit license'
