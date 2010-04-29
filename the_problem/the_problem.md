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
* message is xml
* nested directories
* served via load balanced lighttpd
* load balanced squid cache in front

!SLIDE incremental bullets

# Generation 2 #

* one message per file
* message is xml
* nested directories
* served via load balanced nginx

!SLIDE incremental bullets

# Why this does not work #

* Each file is used for ~1 day
* then rarely used again (keep around for archive)
* wasted space, lots of small files 
* directories with 100k to 1M files
* message volume increases faster than capcity


