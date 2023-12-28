# vim Tricks

Various vim tricks I learn through the years

## Working around quotes

- `f"` or `f'` - jumps to the next quote, assumes cursor within quoted text
- `F"` or `F'` - jumps to the previous quote, assumes cursor within quoted text
- `t"` or `t'` - jumps to the last char before the next quote, assumes cursor within quoted text
- `T"` or `T'` - jumps to the first char after the previous quote, assumes cursor within quoted text

To combine with other commands, we can do the following:

- `df"` - deletes all chars from cursor until the next quote, including the quote itself
- `dt"` - deletes all chars from cursor until the next quote, not including the quote

When used repeatedly, you can do the following shortcut:

- `d;` - repeats the previous quote movement, ie: `t"` or `t'`, then execute the delete command

## Working around brackets or parenthesis or even quotes

To highlight contents within `{}` or `()` or `[]` while inside:

```
vi}
vi)
vi]
```
Note: You can also use the opening bracket but the cursor will jump to it instead.

To delete contents within `{}` or `()` or `[]` while inside:

```
di}
di)
di]
```

Can also work around quotes:

```
vi"
```

Can even work around a world:

```
viw
```

Or a group of text (no spaces in between):

```
viW
```

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
