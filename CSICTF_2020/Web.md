# WEB

# Casade
```
Welcome to csictf.

http://chall.csivit.com:30203
```
This challenge is the easiest one !
Just view source page and we can find the flag in **style.css**
![Image1](https://github.com/wonhee0410/CTF/blob/master/CSICTF_2020/Images/1.png) 

The flag is: **```csictf{w3lc0me_t0_csictf}```**
# Oreo
```
My nephew is a fussy eater and is only willing to eat chocolate oreo. Any other flavour and he throws a tantrum.

http://chall.csivit.com:30243
```
We can guest what we need to do depend on the title of challenge. That's it, oreo or cookie ?
![Image2](https://github.com/wonhee0410/CTF/blob/master/CSICTF_2020/Images/2.png)

So we have a cookie: ```flavor: c3RyYXdiZXJyeQ%3D%3D```
![Image3](https://github.com/wonhee0410/CTF/blob/master/CSICTF_2020/Images/3.png)

Decode in base64, we got ```strawberry```
Let's change this cookie to chocolate in base64 (```Y2hvY29sYXRl```) and refresh the page !

The flag is: **```csictf{1ick_twi5t_dunk}```**

# Warm up
```
If you know, you know; otherwise you might waste a lot of time.

http://chall.csivit.com:30272
```

We got this php code
```
<?php

if (isset($_GET['hash'])) {
    if ($_GET['hash'] === "10932435112") {
        die('Not so easy mate.');
    }

    $hash = sha1($_GET['hash']);
    $target = sha1(10932435112);
    if($hash == $target) {
        include('flag.php');
        print $flag;
    } else {
        print "csictf{loser}";
    }
} else {
    show_source(__FILE__);
}

?>
```
Sha1 of ```10932435112``` is ```0e07766915004133176347055865026311692244```

The comparison ```if($hash == $target)``` show that if the string you type equals ```sha1(10932435112)```, you will get the flag.

I submitted ```10932435112``` to the link, it said ```Not so easy mate.```

It's take me a long time to figure out and I know that is **PHP Type Juggling** (first time I thought magic hash)
https://owasp.org/www-pdf-archive/PHPMagicTricks-TypeJuggling.pdf
https://git.linuxtrack.net/Azgarech/PayloadsAllTheThings/blob/master/PHP%20juggling%20type/README.md

Example:
```
'0x123' == '0x845' is true
'0x123' === '0x845' is false
```
So we can send a request ```http://chall.csivit.com:30272/?hash=aaO8zKZF```

The flag is: **```csictf{typ3_juggl1ng_1n_php}```**


# Mr Rami
```
"People who get violent get that way because they can’t communicate."

http://chall.csivit.com:30231
```
The page shows that we need to check out BroBot at github link. Nooo ! It's a trap.

![Image4](https://github.com/wonhee0410/CTF/blob/master/CSICTF_2020/Images/4.png)

BroBot -> Robot ? -> robots.txt ?

Yes, I got this.

```http://chall.csivit.com:30231/robots.txt```

![Image4](https://github.com/wonhee0410/CTF/blob/master/CSICTF_2020/Images/5.png)

Add to the url ```http://chall.csivit.com:30231/fade/to/black```, we got the flag !

The flag is **```csictf{br0b0t_1s_pr3tty_c00l_1_th1nk}```**


# Secure Portal
```
This is a super secure portal with a really unusual HTML file. Try to login.

http://chall.csivit.com:30281
```
![Image5](https://github.com/wonhee0410/CTF/blob/master/CSICTF_2020/Images/5.png)

Hmm we need to find the password to unlock this thing.

View page source and we got this javascript code 
```
var _0x575c=['\x32\x2d\x34','\x73\x75\x62\x73\x74\x72\x69\x6e\x67','\x34\x2d\x37','\x67\x65\x74\x49\x74\x65\x6d','\x64\x65\x6c\x65\x74\x65\x49\x74\x65\x6d','\x31\x32\x2d\x31\x34','\x30\x2d\x32','\x73\x65\x74\x49\x74\x65\x6d','\x39\x2d\x31\x32','\x5e\x37\x4d','\x75\x70\x64\x61\x74\x65\x49\x74\x65\x6d','\x62\x62\x3d','\x37\x2d\x39','\x31\x34\x2d\x31\x36','\x6c\x6f\x63\x61\x6c\x53\x74\x6f\x72\x61\x67\x65',];(function(_0x4f0aae,_0x575cf8){var _0x51eea2=function(_0x180eeb){while(--_0x180eeb){_0x4f0aae['push'](_0x4f0aae['shift']());}};_0x51eea2(++_0x575cf8);}(_0x575c,0x78));var _0x51ee=function(_0x4f0aae,_0x575cf8){_0x4f0aae=_0x4f0aae-0x0;var _0x51eea2=_0x575c[_0x4f0aae];return _0x51eea2;};function CheckPassword(_0x47df21){var _0x4bbdc3=[_0x51ee('0xe'),_0x51ee('0x3'),_0x51ee('0x7'),_0x51ee('0x4'),_0x51ee('0xa')];window[_0x4bbdc3[0x0]][_0x4bbdc3[0x2]]('9-12','BE*');window[_0x4bbdc3[0x0]][_0x4bbdc3[0x2]](_0x51ee('0x2'),_0x51ee('0xb'));window[_0x4bbdc3[0x0]][_0x4bbdc3[0x2]](_0x51ee('0x6'),'5W');window[_0x4bbdc3[0x0]][_0x4bbdc3[0x2]]('16',_0x51ee('0x9'));window[_0x4bbdc3[0x0]][_0x4bbdc3[0x2]](_0x51ee('0x5'),'pg');window[_0x4bbdc3[0x0]][_0x4bbdc3[0x2]]('7-9','+n');window[_0x4bbdc3[0x0]][_0x4bbdc3[0x2]](_0x51ee('0xd'),'4t');window[_0x4bbdc3[0x0]][_0x4bbdc3[0x2]](_0x51ee('0x0'),'$F');if(window[_0x4bbdc3[0x0]][_0x4bbdc3[0x1]](_0x51ee('0x8'))===_0x47df21[_0x51ee('0x1')](0x9,0xc)){if(window[_0x4bbdc3[0x0]][_0x4bbdc3[0x1]](_0x51ee('0x2'))===_0x47df21['substring'](0x4,0x7)){if(window[_0x4bbdc3[0x0]][_0x4bbdc3[0x1]](_0x51ee('0x6'))===_0x47df21[_0x51ee('0x1')](0x0,0x2)){if(window[_0x4bbdc3[0x0]][_0x4bbdc3[0x1]]('16')===_0x47df21[_0x51ee('0x1')](0x10)){if(window[_0x4bbdc3[0x0]][_0x4bbdc3[0x1]](_0x51ee('0x5'))===_0x47df21[_0x51ee('0x1')](0xc,0xe)){if(window[_0x4bbdc3[0x0]][_0x4bbdc3[0x1]](_0x51ee('0xc'))===_0x47df21[_0x51ee('0x1')](0x7,0x9)){if(window[_0x4bbdc3[0x0]][_0x4bbdc3[0x1]](_0x51ee('0xd'))===_0x47df21[_0x51ee('0x1')](0xe,0x10)){if(window[_0x4bbdc3[0x0]][_0x4bbdc3[0x1]](_0x51ee('0x0'))===_0x47df21[_0x51ee('0x1')](0x2,0x4))return!![];}}}}}}}return![];}
```
It's really complicated beacause that's obfuscated javascript.

Search some tool to deobfuscated code and make some changes by hands, we beautify the code we obtain:

```
'use strict';
/** @type {!Array} */
var _0x575c = ["2-4", "substring", "4-7", "getItem", "deleteItem", "12-14", "0-2", "setItem", "9-12", "^7M", "updateItem", "bb=", "7-9", "14-16", "localStorage"];
(function(data, i) {
    /**
     * @param {number} isLE
     * @return {undefined}
     */
    var write = function(isLE) {
        for (; --isLE;) {
            data["push"](data["shift"]());
        }
    };
    write(++i);
})(_0x575c, 120);
/**
 * @param {string} level
 * @param {?} ai_test
 * @return {?}
 */
var _0x51ee = function(level, ai_test) {
    /** @type {number} */
    level = level - 0;
    var rowsOfColumns = _0x575c[level];
    return rowsOfColumns;
};
/**
 * @param {!Object} results
 * @return {?}
 */
function CheckPassword(results) {
    /** @type {!Array} */
    var easing = ["localStorage", "getItem", "setItem", "deleteItem", "updateItem"];
    window[easing[0]][easing[2]]("9-12", "BE*");
    window[easing[0]][easing[2]]("4-7", "bb=");
    window[easing[0]][easing[2]]("0-2", "5W");
    window[easing[0]][easing[2]]("16", "^7M");
    window[easing[0]][easing[2]]("12-14", "pg");
    window[easing[0]][easing[2]]("7-9", "+n");
    window[easing[0]][easing[2]]("14-16", "4t");
    window[easing[0]][easing[2]]("2-4", "$F");
    if (window[easing[0]][easing[1]]("9-12") === results["substring"](9, 12)) {
        if (window[easing[0]][easing[1]]("4-7") === results["substring"](4, 7)) {
            if (window[easing[0]][easing[1]]("0-2") === results["substring"](0, 2)) {
                if (window[easing[0]][easing[1]]("16") === results["substring"](16)) {
                    if (window[easing[0]][easing[1]]("12-14") === results["substring"](12, 14)) {
                        if (window[easing[0]][easing[1]]("7-9") === results["substring"](7, 9)) {
                            if (window[easing[0]][easing[1]]("14-16") === results["substring"](14, 16)) {
                                if (window[easing[0]][easing[1]]("2-4") === results["substring"](2, 4)) {
                                    return true;
                                }
                            }
                        }
                    }
                }
            }
        }
    }
    return ![];
};
```

It's still very hard to understand, huh ?

We focus on ```function CheckPassword(results)```, it will check the string we type in and compare with the password.

```
if (window[easing[0]][easing[1]]("9-12") === results["substring"](9, 12)) {
        if (window[easing[0]][easing[1]]("4-7") === results["substring"](4, 7)) {
            if (window[easing[0]][easing[1]]("0-2") === results["substring"](0, 2)) {
                if (window[easing[0]][easing[1]]("16") === results["substring"](16)) {
                    if (window[easing[0]][easing[1]]("12-14") === results["substring"](12, 14)) {
                        if (window[easing[0]][easing[1]]("7-9") === results["substring"](7, 9)) {
                            if (window[easing[0]][easing[1]]("14-16") === results["substring"](14, 16)) {
                                if (window[easing[0]][easing[1]]("2-4") === results["substring"](2, 4)) {
                                    return true;
                                }
                            }
                        }
                    }
                }
            }
        }
    }
```

The password has been messed up, just rearrange like this:

```
0-2:"5W"
2-4:"$F"
4-7:"bb="
7-9:"+n"
9-12:"BE*"
12-14:"pg"
14-16:"4t"
16:"^7M"
```

Okay password is ```5W$Fbb=+nBE*pg4t^7M```

Enter that password and we got the flag !

The flag is: **```csictf{l3t_m3_c0nfus3_y0u}```**
