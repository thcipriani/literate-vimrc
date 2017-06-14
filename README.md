# Literate Vimrc

"Literate" Vimrc is more than a bit of a misnomer. It, unlike Donald Knuth's
vision of Literate Programming, does not support a loosely coupled web of macros
-- instead it just lets you write a file in Markdown that has codeblocks (as
defined by [v0.27 of the CommonMark spec](http://spec.commonmark.org/0.27/))
containing Vimscript as your `~/.vimrc` file.

## Install

The intent of this plugin is to create a literate version of your `~/.vimrc`
file. As such, all that needs to be done is to copy the `autoload/literatevimrc.vim` file
into your `~/.vim/autoload` directory, move your current `~/.vimrc` over to `~/.vimrc.md`
(ensuring that the contents of the file are in a Markdown fenced codeblock) and
add the line `runtime! plugin/literatevimrc.vim` to your, now empty, `~/.vimrc`.

### Step by step install

Clone this repo and move the `autoload/literatevimrc.vim` file to `~/.vim/autoload`
```
git clone this ~/src/LiterateVimrc
mv ~/src/LiterateVimrc/autoload/literatevimrc.vim ~/.vim/autoload/
```

Move your old `~/.vimrc` flies to a Markdown file inside a fenced codeblock,
and call the plugin to parse your new "literate" `~/.vimrc.md` inside your
actual `~/.vimrc`.

```
echo "~~~" > ~/.vimrc.md
cat ~/.vimrc >> ~/.vimrc.md
echo 'execute literatevim#load("~/.vimrc.md")' > ~/.vimrc
```
