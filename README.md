java c
CISC2001   Lab   Project   Assignment 
Nov,   2024
1 Reminder 
• Deadline: Before the ﬁnal exam 
2          Assembly Programming Project 
2.1          Task Description 
Design,   code   and   test/debug   an   Aarch64   assembly   program   that   performs   the   following:
1.    Read   in   a   line   of character   which   contains   from   1   to   100   bytes;
2.   The   characters/bytes   represent   UTF-8   encoding   of Unicode   Character;
3.    Count   the   number   of Unicode   characters   in   the   input   stream;
4.   The result of the count should   return   as the   exit   code   of the   program   with   the   following   code:
1 ...
2 // Read i n the string with syscall to read (fd , ∗ buffer , len )
3 mov x0 , #0            // f d for stdin
4 ld r x1 , =buffe r // load the address of buffer to x1
5 mov x2 , #200            // number of character to be read
6 mov w8 , #63            // syscall# for read
7 s vc #0            // invoke the syscall
8
9 // after the call , the number of byte read i n should stored i n x0
10 // and the input bytes are store i n buffer
11 // This i s the part that you should work on your magic
12
13 // i . e . , count the number of Unicode character i n the buffer
14 // After that , assumed that the result was found and stored i n x1
15 mov x0 , x1            // save the result a s exit code i n x0
16 mov w8 , #93            // service # for exit
17 s vc #0
Note: Since   UTF-8   is   a   variable-length   encoding   scheme,   the   number   of   Unicode   characters   will   not   be   the   same   as   the   number   of bytes   in   the   input   string.
2.2 Testing 
•   To   test   your   program,   you   can
1.   download the test-tools.zip ﬁle   in   the   attachment   ﬁles;
2.    copy   the   ﬁle   to   your   emulator   in   the   same   directory   as   your   source   ﬁle,   using   the   scp   command;   (path-1   means   the   path   of test-tools.zip   under   emulator   (windows/macOS))
1  scp    −P    8022          path−1          ubuntu@localhost   :/home/ubuntu/
3.   run   the   following
1  unzip         test   −tools . zip
2  chmod    +x         tester   . sh
3  ./ tester   . sh      yourprogramWhere yourprogram is the name of   your assembly program.   For the ﬁrst two instructions,   you only n代 写CISC2001 Lab Project AssignmentStatistics
代做程序编程语言eed to run them   once.    After that,   each time   you   modify   your   source   code,   you   only   need   to   run   the   last   instruction   to   test   your   updated   program.
•   If   the   unzip   program   is   not   available   in   your   system,   you   need   to   ﬁrst   install   it   with:
1  sudo      apt         install         unzip
•   Note:
– The test-tools.zip   is   now the ﬁnal   version.    It   has   all the   9   seen   test   cases.    When grading   your   assignment,   an   additional   unseen   test   case   will   be   added   to   the   test   system.
– For   some   of   the   test   data,   you   can   see   the   actual   content   if   you   open   them   in   a   text   editor.   Just   keep   in   mind   that   there   is   an   invisible   ”\n”   at   the   end   of   each   data   ﬁle.    So,   the   number   of   characters   in   the   data   should   be   one   more   than   what   you   see   inside   the ﬁle.
2.3          Requirements 
•   The   project   should   be   completed   by   at   most   two   students   in   a   group;
•   Write   the   complete   information   about   your   group   members   at   the   beginning   of   your   source   as   remarks:
1  //      Group      Members   :
2  //       1.      A−B0−1357−9      Chan      Tai      Man
3  //         2.      A−B0−2468−0      Lie      Kai      Ian
•    Submissions   that   fail   to   achieve   any   one   of the   following   will   receive   0   marks:
– The   submission   must   be   made   on   or   before   the   deadline;
– The   submission   must   be   the   source   code   ﬁle   of   the   assembled   language   program;    (i.e.:   ﬁlename.s)
– The   program   must   be   free   of syntax   error   and   must   be   able   to   be   assembled   and   linked   successfully   by   the   test   system;
– The   program   must   pass   at   least   one   of the   test   cases   in   the   test   system;
•   Marking
– Please   fully   document   your   code;
– Your   ﬁnal   mark   is   directly   proportional   to   the   number   of   test   cases   that   your   program can   pass;
2.4          Files to be submitted 
•    Source   code   ﬁle   (i.e.:   ﬁlename.s);
•   Project   report   (including   screenshots   of   experimental   results.).

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
