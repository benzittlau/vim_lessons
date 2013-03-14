Called 'syntax', 'syntax-highlighting', or 'coloring'

* Helpful hint, you can execute any of the commands I recommend
* you type by selecting the text and yanking, and then using the command
* :@" to execute what is in your default register

* Super 1337 hint.  Yank the following line into register a `"ayy`
f:lyt`:@"
* Now you can execute any of my example commands by placing your
* cursor at the start of the line and typing "@a"

First, let's reset your colors.  

# Highlight the lines below and yank into your default register
# Type `:@"` to execute the commands
set background=light
highlight clear
if exists("syntax_on")
  syntax reset
endif

The `:highlight` command will allow you to configure different 'highlight groups'
with a chosen color.

If you are in a cterm, try:
# Type `:highlight Normal ctermbg=black ctermfg=white guibg=black guifg=white`

Pretty, isn't it!

The highlight allows you to apply styling to a `highlight group`.  Assuming we are all
dealing with color terminals or graphical vims, these are the available commands that
can be passed to highlight:

          GUI                        CTERM
    gui={attr-list}              cterm={attr-list}
    font={font-name}
    guifg={color-name}           ctermfg={color-name}
    guibg={color-name}           ctermbg={color-name}

Any number of the above commands can be used in a single call to 'highlight'.  The
commands that don't apply to your given vim type will be ignored.  Note that our example
above used commands for both the GUI and for CTERM, so it will work for both.

The 'Normal' means we're setting colors for the normal highlight group.
Let's try setting colors for 'Visual' highlight group!

Try:
# Type `:highlight Visual ctermbg=red ctermfg=blue guibg=red guifg=blue`

Now checkout what we did by pressing 'V' to enter visual mode.  
Takes me back to my mIRC days...


So what do 'gui' and 'cterm' do?  These can apply additional non-color
stylings to a highlight group.  Let's have some fun:

# Type `:highlight htmlH2 gui=underline cterm=bold`
## If you are using a gui vim this text is now underlined!
## If you are using a cterm vim this text is now bold!

There are a few other options you can play with here...
# Type `:highlight htmlH3 gui=standout,reverse cterm=standout,reverse`
### Test text


You might be familiar with colorscheme's in VIM.  Colorscheme's
are generally just a list of highlight calls, defining what different
highlight groups should look like in that theme.  I've put an example
colorscheme in the 'syntax' folder in this project. I recommend
you go look at the file now.  If you're too lazy, here's an example
line from the file

# highlight Search                    guifg=NONE ctermfg=NONE guibg=#2b2b2b ctermbg=235 gui=italic cterm=underline

You should now be able to understand what each of the parts of that
command are doing.





Things to talk about
highlight groups
  - how to color them

cterm vs term vs gui

256 colors vs 16 million colors

useful online tools

colorschemes

random cool thing :TOhtml
