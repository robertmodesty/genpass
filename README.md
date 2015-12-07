*** Rotary Random Password Generator ***

  This is a stand-alone, human readable and portable single file random password generator wrote in BASH script.  The "stand-alone" here means it avoid to use any external command, for reducing security vulnerabilities.  You can use it to generate passwords applicable to many occasions, such as computer login, bank debit card, WiFi security, etc.

  Why not build this with C language?  The first, C program need to be compiled, so it is not so portable for regular users.  Today we have BASH on many computer systems, users only need to copy the file or even the text and then run it.  Second, shell script executable code is actually the source code, and human readable.  User can review it without wondering if the executable code match the source code.  This is an advantage on programs about security.  Over here a malware can only be the system or the interpreter that can identify this generator.  The last, for an interactive program, the high performance of C language is not the primary consideration.

  This program generates characters for password like rolling a rotor and pause it suddenly by pressing [Enter] key.  This make the password unpredictable.  The length of password, what characters as candidates, can be specified by arguments.

  In the 'Auto' mode, the generator does not "roll the rotor", but use the /dev/random as random pool instead.  In some OS, this may cause the password predictable.  It may not be a good idea using this mode.  But, this mode make the script able to be called by other script or program as a password source.  The other program can get a password through this script, and use it as an one-time-password or on some automated operation.

  For security reasons, there is a mini version named "gnpas".  User can read it fast and easily, edit the setting in it, and execute it by commanding './gnpas'.  The mini version does not need any command argument.

  To use this, just get prepared, then execute this program and get the password.  DO NOT re-generate a password for some unimportant reasons. Over filtering will turn your random password predictable.  For example, throwing away nine passwords from ten only because they are too hard to remember, then only 10% of all possible passwords will be use.  An attacker may speed up ten times on guessing it by knowing that.

 -- Easy passwords aren't strong, strong passwords aren't easy. --

SYNOPSIS

        ./genpass [-a] [-c|-n] [length of password] [l][u][n][s] [-s ...]

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

