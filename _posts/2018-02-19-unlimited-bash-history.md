---
layout: post
title:  "Unlimited Bash history"
categories: linux bash
---

I find the following Bash history settings invaluable and use them on every Ubuntu terminal I can.

When you use `Ctrl+Shift+R` in bash it searches in reverse through your previously run commands. These commands are usually stored in a `.bash_history` file, but only for a limited number of commands. These following instructions enable an unlimited history for all your previously run commands [[source](https://stackoverflow.com/a/19533853/690188)]:

> First, you must comment out or remove this section of your `.bashrc` (default for Ubuntu). If you don't, then certain environments (like running screen sessions) will still truncate your history:

{% highlight bash %}
# for setting history length see HISTSIZE and HISTFILESIZE in bash(1)
# HISTSIZE=1000
# HISTFILESIZE=2000
{% endhighlight %}

> Second, add this to the bottom of your .bashrc:
{% highlight bash %}
# Eternal bash history.
# ---------------------
# Undocumented feature which sets the size to "unlimited".
# http://stackoverflow.com/questions/9457233/unlimited-bash-history
export HISTFILESIZE=
export HISTSIZE=
export HISTTIMEFORMAT="[%F %T] "
# Change the file location because certain bash sessions truncate .bash_history file upon close.
# http://superuser.com/questions/575479/bash-history-truncated-to-500-lines-on-each-login
export HISTFILE=~/.bash_eternal_history
# Force prompt to write history after every command.
# http://superuser.com/questions/20900/bash-history-loss
PROMPT_COMMAND="history -a; $PROMPT_COMMAND"
{% endhighlight %}

> It gives you an unlimited bash history that also records the time the command was run and saves the command instantly instead of waiting till you exit your session.
