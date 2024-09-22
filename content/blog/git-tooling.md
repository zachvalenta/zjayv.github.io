+++
title = "Git tooling"
date = 2024-09-22
draft = true
+++

GUI
* alternatives https://git-scm.com/downloads/guis/ https://git-scm.com/book/en/v2/Appendix-A%3A-Git-in-Other-Environments-Graphical-Interfaces
* _GitUP_: ✅ https://github.com/git-up/GitUp
* good for granular stages
* switch views `cmd #`
* open commit into quick view `space`

PAGER / DIFFVIEW
* set to use external tool via `git difftool -help` 📙 Chacon [2.54]
* _diff-so-fancy_: ✅ https://github.com/so-fancy/diff-so-fancy
* _delta_: diffs/filenames were too dark https://github.com/dandavison/delta node version https://news.ycombinator.com/item?id=27007844
* _difftastic_: 🎯 https://github.com/Wilfred/difftastic
* _diffview_: 🎯 neovim https://github.com/sindrets/diffview.nvim https://www.youtube.com/watch?v=aJikrPnTOtI
* _dunk_: https://github.com/darrenburns/dunk

PORCELAIN
* _bit_: autcomplete https://github.com/chriswalz/bit
* _forgit_: good UI, clunky install https://github.com/wfxr/forgit#-features
* _gitbutler_: https://github.com/gitbutlerapp/gitbutler https://blog.gitbutler.com/
* _gitsigns_: 🎯 Neovim, similiar to vim-fugitive, catppuccin integration https://github.com/lewis6991/gitsigns.nvim
* _lazygit_: 🎯 popular, good UI https://github.com/jesseduffield/lazygit https://github.com/catppuccin/lazygit https://www.youtube.com/watch?v=Ihg37znaiBo
* _magit_: looks great, Emacs-only https://github.com/magit/magit https://emacsair.me/2017/09/01/magit-walk-through/ https://github.com/dandavison/delta/issues/194
* _Neogit_: 🎯 magit port https://github.com/NeogitOrg/neogit
* _vim-fugitive_: 🎯 https://github.com/tpope/vim-fugitive https://www.youtube.com/watch?v=kFVjoIish0E https://gumroad.com/vimtricks https://github.com/TimUntersberger/neogit http://vimcasts.org/episodes/archive/ https://www.semicolonandsons.com/episode/IDE-like-refactors-snippets-tests-hover-docs-commenting-and-git 3:15 http://vimcasts.org/episodes/archive/ https://www.youtube.com/watch?v=F7JZdAwGmpU https://www.youtube.com/watch?v=vpwJ7fqD1CE https://nimbleind.gumroad.com/l/hsOVI
* _vimagit_: https://github.com/jreybert/vimagit

REPO BROWSER
* _gitk_: https://git-scm.com/docs/gitk
* _grv_: https://github.com/rgburke/grv
* _serie_: https://github.com/lusingander/serie
* _Tig_: ✅ https://github.com/jonas/tig https://jonas.github.io/tig/doc/manual.html
* modes: main `m` diff `d` log `l` blame `b`; main view with message body https://github.com/jonas/tig/issues/1032
* all commits: `tig` in repo
* file history: `tig path/to/file`
* blame: `tig blame path/to/file` https://stackoverflow.com/q/15304804 or tree view `t` then `b`
> binding to view full file https://www.youtube.com/watch?v=goNodOWENEg