!SLIDE transition=toss

# The Problem #

!SLIDE incremental bullets

# We collect data #

* blogs
* message boards
* twitter
* news articles
* facebook public pages

!SLIDE 

# Where to store it? #

!SLIDE incremental bullets

# Generation 1 #

* one message per file
* file is xml
* files are nested in directories
* served via load balanced lighttpd
* load balanced squid cache in front

!SLIDE incremental bullets

# Generation 2 #

* one message per file
* file is xml
* file are nested in directories
* served via partitioned and load balanced nginx
* routed with HAproxy 

!SLIDE incremental bullets

# Why this does not work #

* Each file is used for ~1 day (access ~10 times)
* then rarely used again (keep around for archive)
* directories with 100K to 1M files
* wasted space, 4KiB disk block, 2KiB files
* message volume increases faster than capacity
* write to 2 locations (for backup)

