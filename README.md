# ZCracker

=========A zip password cracker written in Python by python-scripter==========

Requirements:
Python's standard library can't handle rar files so you have to install unrar module:

pip install unrar

Windows users: if you get an exception when trying to retreive rar file passwords you probably need to download unrar.dll and copy it to windows/system32 folder (google is your friend)
==============================================================================

Example:

import ZCracker as zc

mission = zc.CrackZip('d:\\\lockedzip.zip')

Or, if you want to work on a .rar file:

mission = zc.CrackRar('d:\\\lockedrar.rar')

to start a dictionary attack:

p = mission.dict_attack()

print('password found:', p)

to start a Brute-Force attack:

p = mission.brute_attack(min_length=5, max_length=6, space_n=4)

If you're wondering what space_n refers to:

space = zc.selector()

For space_num in spaces
   Print(space_num, ':', spaces[space_num])
   
print('password found:', p)

PS: currently, brute-force attacks do not look for white-spaces in the password string. And you really shouldn't try a full scale brute-force attack unless you have a supercomputer cause it can take ages.
===============================================================

If you have a custom dictionary list file you want to use instead of the included dictionary (which is advisable, since the included dict  contains words only), you can convert it to  pickle using the  gen_dict() function.

Example:

from ZCracker import gen_dict

gen_dict('dictionary.txt', 'dictionary.pickle', separator='\n')

Note that if the passwords in your dictionary.txt file  are separated by anything other  a new line (which is rare), you must pass the limiter as the separator argument.

For example, of  you have a blank line between every 2  passwords:
gen_dict('dictionary.txt', 'dictionary.pickle', separator='\n\n')
=============================================================

If you have any suggestions or  if you notice any bugs, please let me know!
