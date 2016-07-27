# SPEC-CPU2006-tools-building-for-ARM
mount -t iso9660 -o ro,exec *.iso target_directory
sudo cp target_directory/* Install_directory
cd Install_directory
change the permissions and ownership
sudo chmod -R 777 *
sudo chown -R username:username *
upgrade the gnulib for solving 'gets' problem 
bash buildtools
change in specsum lib: stdio.h file
Miniperl ld error
 Ensure /bin/sh is bash. Dash won't work.
Perl needs libm to fix errors like:

 #cc -L/home/cbuild/tools/output/lib -L/usr/local/lib -o miniperl miniperlmain.o opmini.o libperl.a libperl.a(pp.o): In function `Perl_pp_pow': pp.c:(.text+0x1ba0): undefined reference to `pow'

Set via

export PERLFLAGS="-A libs=-lm -A libs=-ldl"

*** You should add the above line within the tools/src/buildtools file. (Right above of ./Configure ... line) It didn't work when I added the line in .bashrc and source it. I spent so long time to figure this out.

Somewhere during asks for user to enter 'y' for failing to do some perl tests
