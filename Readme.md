Welcome to the red spider project. We have fun here.


### Why ###

Because we like to combine our love for the xkcd comic with our love for coding, and we want to share the experience.


### Who ###

Currently, "we" are all members of the [xkcd forums](http://forums.xkcd.com). However, anyone is welcome to join in.


### How ###




### THE GOAL ###

-    To have an enjoyable time collaborating with fellow xkcdians on an ongoing coding project.
-    To write code that is interesting or amusing for others to read, or both.
-    To write programs that give you a fuzzy "xkcd feeling" when used, because they produce amusing, interesting or touching output (or a combination).
-    To make a cozy, messy web of programs that may sometimes call other programs, possibly in unanticipated ways.
-    To go crazy.


### THE MEANS ###

-    A publicly hosted repository that people can easily get write access to.
-    A permissive license that applies to all parts of the project.
-    Platform neutrality: terminal only, programs interoperate with exit statuses, pipes and file redirection. This is kind of unixy but it works fine on Windows as long as you keep it simple.
-    Many small though not necessarily independent programs, rather than one monolithic thing. This makes it easier for people with little time or short attention spans to join in, while still allowing for collaboration.
-    All (free of charge) programming languages are welcome and encouraged. The more diverse the better.
-    An open-minded attitude: all ideas are interesting. There are no limits on what a program may do, except that it must not be malware.
-    A more-or-less fixed, simple directory structure so things can be found and automated.
-    A common build system so all compiled stuff can be installed in one go, for example with CMake.


### DETAILS ###

Root directory contents (please mentally translate forward slashes to backward slashes if that comforts you):

-    bin/: installed commands. No subdirectories.
-    lib/: installed run-time and link-time dependencies of the commands. Not just binaries, e.g. also Python objects or awk filters that are meant to be used by a shell script. No subdirectories.
-    build/: anything produced by the makefiles that is not supposed to go into bin/ or lib/. Assuming that we use CMake, this includes platform-specific makefiles generated from the CMakeFiles. Subdirectories depend on the whims of the build tool.
-    include/: all source files that are meant to be included/imported in other source files. No subdirectories.
-    src/: all other source files as well as the makefiles of individual programs. For many small programs written in a scripting language, "installing" it will be nothing more than copying it from src/ to bin/. Subdirectories are avoided unless a single program uses lots of source files. Reason: this encourages people to read code from others and forces them to avoid name clashes.
-    test/: tests for the projects in src/, possibly run during installation. The majority of programs don't have or need a separate test program; it should be sufficient to just run them as a means of testing.
-    doc/: if anyone feels an urge to write proper documentation, they can put it here. HTML and plaintext are preferred. Subdirectories if the documentation to a given command consists of more than one file.
-    config/: optional configuration files for the user. Only sensible if we write commands that make use of configuration files. No subdirectories.
-    work/: any other user files, possibly generated by the commands in bin/. Subdirectories at will. A "master" makefile that builds and installs everything. Exception: programs that require payware or that aren't portable between Windows and unixy systems. "make clean" (or whatever that command is going to look like) erases everything from bin/, lib/ and build/.
-    A .gitignore file. Everything that is not in src/, include/, doc/ or directly in the root directory should be ignored by the VCS.
-    License.txt: the xkcd-ified MIT license (or whatever we're going to use as the default license). Source files that are native to the xkcd hacking project should refer to this file.
-    Readme.txt: how to install, how to use, how to hack, any caveats with regard to the license (e.g. if we happen to copy LGPL'ed libraries), etcetera.
-    Dependencies.txt: list of all third-party software that one needs to have installed in order to be able to run the master makefile and the commands that are installed by it. With pointers so people don't need to search everything on the internet first. Optionally also a list of payware/platform-specific software that will enable more commands.
-    Authors.txt: anybody and everybody who's contributed to the project. Feel free to add your name to the list when you commit.
-    Things that we forgot about.


### OTHER STUFF ###

-    If it's not on the master branch, it doesn't *have* to be platform-independent.
-    All contributions are welcome. Seriously.
-    Look to the following thread for updates, discussion and archaeology: [red spider project](http://forums.xkcd.com/viewtopic.php?f=11&t=81969)
