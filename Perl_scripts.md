##Perl scripts on Beocat

When learning to run Perl code you should save your code in plain text files on Beocat (the same way that you do for Bash shell scripts).

Perl scripts should always start with the following lines:

```
#!/usr/bin/perl
#	USAGE: 
# DESCRIPTION: 
use strict;
use warnings;
```

Line one must be the shebang. You should include a usage statement and description so that you or anyone else can quickly find out how to run your script. "use strict" and "use warnings" cause Perl to report potential bugs or unusual code to you. These speed up debugging your code.

After these five lines add the Perl code that you want to run, save your file and make it executable with `chmod`.

```
chmod 755 my_perl_script.pl
```

Now you can run your code with:

```
./my_perl_script.pl
```
