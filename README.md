# bashcolor
Bash color settings for Ubuntu (or debian based distros)

## Step 1 - Initialize
Find the following code in you .bashrc file (typically ~/.bashrc or /home/YOUR_USERNAME/.bashrc)
It may not be exact, but the important part is the `if [ "$color_prompt" = yes ]` and the `PS1=` line.
```
if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '    #original
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
fi
```
Add the following code above the block mentioned above to enable easier color variables.

```
# ANSI color codes
RS="\[\033[0m\]"    # reset
HC="\[\033[1m\]"    # hicolor
UL="\[\033[4m\]"    # underline
INV="\[\033[7m\]"   # inverse background and foreground
FBLK="\[\033[30m\]" # foreground black
FRED="\[\033[31m\]" # foreground red
FGRN="\[\033[32m\]" # foreground green
FYEL="\[\033[33m\]" # foreground yellow
FBLE="\[\033[34m\]" # foreground blue
FMAG="\[\033[35m\]" # foreground magenta
FCYN="\[\033[36m\]" # foreground cyan
FWHT="\[\033[37m\]" # foreground white
BBLK="\[\033[40m\]" # background black
BRED="\[\033[41m\]" # background red
BGRN="\[\033[42m\]" # background green
BYEL="\[\033[43m\]" # background yellow
BBLE="\[\033[44m\]" # background blue
BMAG="\[\033[45m\]" # background magenta
BCYN="\[\033[46m\]" # background cyan
BWHT="\[\033[47m\]" # background white
```

## Step 2 - Customize
Edit the content after `PS1=`  on the first line to customize your bash prompt. 
*I recommend commenting out the existing line and saving it as a backup (simply add a # in front of PS1 to disable that line).*

To use a variable mentioned in step 1, simple insert a `$` in front of the variable name.

**Make sure to include a `$RS` reset at the end of your custom prompt to ensure your command outputs aren't affected by your .bashrc**

Example: 
`PS1="$FBLE[ $HC$FGRN${debian_chroot:+($debian_chroot)}\u$FWHT: $RS$FGRN\w $FBLE]$HC$FWHT$ $RS"`

The above example looks like:

![alt text](https://ibmc.site/misc/bashrc.jpg "Bash example")


