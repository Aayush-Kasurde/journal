vim rc
======

filetype plugin on

inoremap  ,   , <Space>

inoremap  (  ()<Left>

inoremap  [  []<Left>

inoremap  {  {}<Left>

vnoremap  (  s()<Esc>P<Right>%

vnoremap  [  s[]<Esc>P<Right>%

vnoremap  {  s{}<Esc>P<Right>%

highlight OverLength ctermbg=red ctermfg=white guibg=#592929
match OverLength /\%81v.\+/

syntax off
