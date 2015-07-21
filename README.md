*** Rotary Random Password Generator ***

  This is a real random password generator wrote in BASH script.  You can use it to generate passwords applicable to many kinds of place, such as computer login, bank debit card, WiFi security, etc. 

  It generate characters for password like rolling a rotor and pause it suddenly by pressing [Enter] key.  This make the password unpredictable.  The length of password, what characters as candidates, can be specified by arguments.

  IN the 'Auto' mode, the generator does not "roll the rotor", but use the /dev/random as random pool instead.  In some OS, this may cause the password predictable.  It may not be a good idea using this mode.

  To use this, just get prepared, then execute this program and get the password.  DO NOT re-generate a password for some unimportant reasons. Over filtering will turn your random password predictable.  For example, throwing away nine passwords from ten only because they are too hard to remember, then only 10% of all possible passwords will be use.  An attacker may speed up ten times on guessing it by knowing that.

 -- Easy passwords aren't strong, strong passwords aren't easy. --

SYNOPSIS

        genpass [-a] [-c|-n] [length of password] [l][u][n][s] [-s ...]

ARGUMENTS

        l   lowercase   
        u   uppercase
        n   numbers
        s   other symbol

        -e
          easy mode, use 'lsunln' as the composition of the candidates

        -a
          auto generate from /dev/random ( NOT RECOMMENDED! )

        -c
          show password in different colors

        -n
          show password uncolored

        -s
          use the following string as candidates

