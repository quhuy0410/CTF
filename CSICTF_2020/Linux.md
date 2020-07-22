# LINUX

# AKA

```
Cows are following me everywhere I go. Help, I'm trapped!

nc chall.csivit.com 30611
```

Try ```ls```

```
wonhee0410$ nc chall.csivit.com 30611
user @ csictf: $ 
ls 
 ________________________________________
/ Don't look at me, I'm just here to say \
\ moo.                                   /
 ----------------------------------------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

```
user @ csictf: $ 
ls *    
 ________________________________________
/ Don't look at me, I'm just here to say \
\ moo. flag.txt script.sh start.sh       /
 ----------------------------------------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

There are 3 files.

After a short time of searching google, I know that a command aka ```ls``` is ```nl```

```
user @ csictf: $ 
nl *
     1	csictf{1_4m_cl4rk3_k3nt}
     2	shopt -s expand_aliases
     3	alias cat="cowsay Don\'t look at me, I\'m just here to say moo."
     4	alias ls="cowsay Don\'t look at me, I\'m just here to say moo."
     5	alias grep="cowsay Don\'t look at me, I\'m just here to say moo."
     6	alias awk="cowsay Don\'t look at me, I\'m just here to say moo."
     7	alias pwd="cowsay Don\'t look at me, I\'m just here to say moo."
     8	alias cd="cowsay Don\'t look at me, I\'m just here to say moo."
     9	alias head="cowsay Don\'t look at me, I\'m just here to say moo."
    10	alias tail="cowsay Don\'t look at me, I\'m just here to say moo."
    11	alias less="cowsay Don\'t look at me, I\'m just here to say moo."
    12	alias more="cowsay Don\'t look at me, I\'m just here to say moo."
    13	alias sed="cowsay Don\'t look at me, I\'m just here to say moo."
    14	alias find="cowsay Don\'t look at me, I\'m just here to say moo."
    15	alias awk="cowsay Don\'t look at me, I\'m just here to say moo."
       
    16	while :
    17	do
    18	    echo "user @ csictf: $ "
    19	    read input
    20	    eval $input 2>/dev/null
    21	done
    22	#! /bin/sh
       
    23	cd /ctf
    24	/bin/bash script.sh
```

The flag is: **```csictf{1_4m_cl4rk3_k3nt}```**
