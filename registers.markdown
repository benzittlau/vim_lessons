Called "registers"

Registers can be thought of as buffers which can store text.  They can be used
both to store raw text, but also to store macros.  A register is being used
any time you copy, paste, or delete in vim.

Can view currently defined registers using :reg or :display

Default register is '"'


Can be used for copy and paste

Copy:
"kyy

Paste:
"kp

# Copy this text into register k `"kyy`
# Now paste the text below here `"kp`


Register 0 always contains the text from the most recent yank command


# Copy this text `yy`
#
# Delete this text `dd`
#
# Now paste the first text below here`"0p`

Register 1 always contains the text from the most recent delete command

# Delete this text `dd`
#
# Copy this text `yy`
#
# Now paste the first text below here`"1p`

Registers 2 through 9 contain the history of deletes

# Line 1: Delete this text `dd`
# Line 2: Delete this text `dd`
# Line 3: Delete this text `dd`
# Line 4: Delete this text `dd`
# Line 5: Delete this text `dd`
#
# Now paste the lines in order below this text `"1p, "2p, "3p, "4p, "5p`

# Line 1: Delete this text `dd`
# Line 2: Delete this text `dd`
# Line 3: Delete this text `dd`
# Line 4: Delete this text `dd`
# Line 5: Delete this text `dd`
#
# Now do the same thing using . to repeat the operation and it will cycle through the number registers `"1p, ., ., ., .`


The 'Named' registers 'a-z' are only set with data when you explicitly use them
Capital versions are *not* independent registers
* use lower case to overwrite the registers contents
* use UPPER CASE to append to the registers contents 

# Copy this line into register a `"ayy`
# Copy this line into register b `"byy`
# Append this line to register a `"Ayy`
#
# Now paste the two lines in register 'a' `"ap`


There are also some 'read-only' registers
* '.' contains the last inserted text
* '%' contains the name of the current file
* '#' contains the name of the alternative file
* ':' contains the last used command text

# On the line below, paste the name of the current file `"%p` 
# 
# Now type something on the line below and paste it again using `".p`
# 


# Put your cursor on the line below and run the following command `:s/\`\w\+\`/<\1>/`: hint, copy it run it from there `@"`
# word
# Now put your cursor back on that line, and bracket word three times using `3@:`


A cool trick, you can copy all the lines matching a regex to a register

# Run `qaq` to clear the 'a' register, and then run `:g/^# Error/y A` to append all lines starting with Error to A
# Error: First error!
# Notice:
# Warning:
# Error: Second error!
# Notice:
# Notice:
# Error: Third error!
# Now call `"ap` to paste the errors



for more see
:shelp registers


Btw, vimgolf! http://vimgolf.com/
