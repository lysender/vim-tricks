# vim Tricks

Various vim tricks I learn through the years

## Working around quotes

- `f"` or `f'` - jumps to the next quote
- `F"` or `F'` - jumps to the previous quote
- `t"` or `t'` - jumps before the next occurrence of quote
- `T"` or `T'` - jumps after the previous occurence of quote

To combine with other commands, we can do the following:

- `df"` - deletes all chars from cursor until the next quote, including the quote itself
- `dt"` - deletes all chars from cursor until the next quote, not including the quote

When used repeatedly, you can do the following shortcut:

- `d;` - repeats the previous `t` or `T` or `f` or `F` motions, ie: `t"` or `t'`, then execute the delete command

## Working around brackets or parenthesis or quotes

To highlight contents within `{}` or `()` or `[]` or `""` while inside:

- `vi}`
- `vi)`
- `vi]`
- `vi"`
- `vi'`
- `viw` - highlight a word
- `viW` - highlight a word (can contain punctuation)

Note: You can also use the opening bracket or parenthesis.

## Using nvim-surround

With `nvim-surround` plugin installed, we can do the following where; `*` is the cursor position:

```
    Old text                    Command         New text
--------------------------------------------------------------------------------
    surr*ound_words             ysiw)           (surround_words)
    *make strings               ys$"            "make strings"
    [delete ar*ound me!]        ds]             delete around me!
    remove <b>HTML t*ags</b>    dst             remove HTML tags
    'change quot*es'            cs'"            "change quotes"
    <b>or tag* types</b>        csth1<CR>       <h1>or tag types</h1>
```
