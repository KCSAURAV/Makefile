# Makefile
General use of makefile. These are demos to help with make commands.

RUNNING MAKE

To run the make command, make sure your working directory has a makefile 
in it. If it is not one of the standard names described above you can use the 
-f option to the make command. If the makefile is named MAKEFILE, you would type

    make -f MAKEFILE // Use name "MAKEFILE"

NOTES:

Touch will create an empty file without modification in compiling
Or if it already has a file it will update

    touch dummyfile // will also create it

rm dummyfile

rm *.o // will delete all .o files

make main.o // will only create make.o

else make command will compile the first object demo

make clean // will delete object files

.PHONY: clean // will not create clean file but runs .Tells make that it is a fake target

clean:
    \rm *.o
    
        ^
        |

Give an unaliased version of the file

install: demo

    \cp demo ../bin   -> will create a copy of demo and name it install and puts it in dir /bin
    touch install

install2: demo

    if [ ! -d ../bin ] ; then mkdir ../bin ; fi //if bin does not exist create a dir /bin
    \cp demo ../bin
    touch install2

tar: *.c *.h
    
    if [ ! -d demodir ] ; then mkdir demodir ; fi
        ln -f Makefile *.c *.h demodir/
        tar -czf demo.tar.gz demodir
        rm -rf demodir


ln - > create links
-czf ->compress the files in the directory

rm -> removes the demodir


Makefile will create variables or use them

all: $(EXEC)



grep 
find . -name 'Makefile'

to use that instead. If you do not want make to do anything but just want to
see what make might do, use the -n option, which does not execute any commands
but just displays which ones it would do:

    make -n

There are many other things to know about running make, but these two flags
are useful to remember as you progress through the lessons.

Lastly, the makefile in this top-level directory is the LAST part of this 
tutorial. You will not understand it until you have finished the tutorial.
Save it for last :)

