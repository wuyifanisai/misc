#|         
#|                  ####     ##     #####
#|                 #    #   #  #      #
#|                 #       #    #     #
#|                 #  ###  ######     #
#|                 #    #  #    #     #
#|                  ####   #    #     #
#|
#|                 Chinese Input Method

# The Script to Generate My Own Chinese Input Method Gat Char Key Tables
# Gat: https://github.com/district10/gat

Varable Length Encoding
-----------------------

Overall
-------

+-----+--------------+----------------------+------------------------------------+
| 1g  |   one gram   |           [?]        | [?]: [{a..y} - {e,t}]		 |  
+-----+--------------+----------------------+- ----------------------------------+
| 2g  |  two grams   |        [e] + [?]     | [?]: [{a..y} - {t}]		 |  
+-----+--------------+----------------------+------------------------------------+
| 3g  | three grams  |    [t] + [?] + [?]   | [?]: [{a..y} - {e}]; [?]: [{a..y}] |
+-----+--------------+----------------------+------------------------------------+
| 4g  |  four grams  |     [e]+[t]+[?]+[?]  | [?]: [{a..y}] both of them	 |
+-----+--------------+----------------------+------------------------------------+
| 5g  |  five grams  |   [t]+[e]+[?]+[?]+[?]| [?]: [{a..y}] all of them		 |
+-----+--------------+----------------------+------------------------------------+


Design Strategies
-----------------
 0. All that matters, is speed and comfort.
 1. Letter "z" is reserved. 
 2. See my Script & Gat-tables folder for more infomation.
 3. All We care is Efficiency, and we don't want to watch and choose 1/2/3, that really kills me.
 4. Keys are binded to my neo-extended dvpe keyboard layout.
 5. I haven't learned it yet.(I'm busy)
 6. In Gat-tables, 'E' means letter 'e', and 'l', meaning left (left hand side), r, right hand side.
 7. According to easiness to type, keys of left hand sides are categoried into 4 groups, reffered as la, lb, lc, ld. And lA is la + 'e'. Similar for Right hand side letters.
 8. Left Right Alternation as the strategy to fasting typing.

    
Scripts How To
--------------
 1. Compile the c file: `gcc gen-gen-gat.c -o gen-gen-gat.bin`
 2. Run gen-gat.sh as `bash gen-gat.sh` to generate all scripts and tables
 3. Run assemble.sh to assemble them to one table, `bash assemble.sh`
 4. Run bind-key-value.sh to bind keys generated by me and values downloaded from internet (https://github.com/district10/misc/tree/master/gen-gat/zh_chars)
 5. Use this table to generate an el package, then we can use it in emacs. 
    1. `pr -m -t -s\  keys.txt vaules.txt | gawk '{printf "(%s, ?%s)\n", $1,$2}'`
    2. And, 可以用脚本简单的把码表映射到别的键盘布局下。如这个文件 gat-key-value-6000.dvp.txt 就是 dvp 的码表。用这个脚本转换： https://github.com/district10/dotfiles/tree/master/scripts
    3. Finally, 从码表生成 el 文件，也有一个简单的脚本。还是上方的链接。


=======================================================================

Level 1
=======

+------+------+------+------+------+------+------+------+------+------+
|  ;   |  ,   |  .   |  有  |  们  |  上  |  大  |  为  |  和  |  z   |
+------+------+------+------+------+------+------+------+------+------+
|  是  |  一  |  e   |  的  |  人  |  以  |  国  |  t   |  这  |  了  |
+------+------+------+------+------+------+------+------+------+------+
|  他  |  我  |  个  |  在  |  不  |  要  |  中  |  会  |  地  |  _   |
+------+------+------+------+------+------+------+------+------+------+

Level 2
=======

+------+------+------+------+------+------+------+------+------+------+
| nil  | nil  | nil  |  出  |  成  |  种  |  作  |  生  |  来  | nil  |
+------+------+------+------+------+------+------+------+------+------+
|  可  |  年  |  e   |  能  |  行  |  用  |  对  |  t   |  时  |  到  |
+------+------+------+------+------+------+------+------+------+------+
|  学  |  自  |  经  |  而  |  发  |  法  |  于  |  所  |  就  | nil  |
+------+------+------+------+------+------+------+------+------+------+

Level 3
=======
Level 4
=======
Level 5
=======
