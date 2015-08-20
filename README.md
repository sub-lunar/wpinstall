# wpinstall

Shell script to install a new WordPress in a subdirectory of the current dir

## Dependencies/Prerequisites

wpinstall expects you to have the `wpsalt` script installed. (For `wpsalt`,
look at my other repo.)

Also, it assumes you are running the web server and database on the same
host and have access to mysql via the command line WITHOUT explicitly passing
credentials (you should keep those in ~/.my.cnf)

(I wrote it to quickly install new WordPress systems for development on
my local machine.)

Other than that, it should run in pretty much every
*nix environment with basic gnu tools installed.

Oh, and you need a working internet connection, of course, to download
WordPress itself and generate the salt.

## Installation

0.  Either git clone this repository or just download the `wpinstall` file
0.  Move or symlink the wpinstall file to a directory inside your shell’s
    path, e.g. `/usr/local/bin/` or `~/bin/`. I prefer the latter because
    it can be done without root privileges and I don’t see why you’d need
    to install a script like wpinstall system wide ...
0.  Make sure that the `wpinstall` is executable. If you git cloned you
    should be ok. If you just downloaded the file, run
    `chmod +x wpinstall` (inside the directory wherever you put it, of course)

## Usage

0.  Open the wpinstall file in a text editor. There are two variables declared
    at the top of the file: db_user and db_pass. These will be used to
    generate your `wp-config.php` files, so put the username and password for
    mysql in there. This is the only configuration, so I thought we wouldn’t
    need an extra config file.
0.  Go to the docroot of your web server
0.  Run `wpinstall <name>` where <name> will be the directory name of your
    new WordPress AND the database name, so you better only have characters
    in underscores in there. You can of course just rename the directory
    afterwards if you wish so.
0.  Point your browser to the url of your WordPress and complete the
    installation.

