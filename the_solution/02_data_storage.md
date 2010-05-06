!SLIDE incremental bullets transition=toss

# Part 1 - Message Storage System #

* must store 1 billion messages (per year)
* efficient use of disk space
* accessible via a "key"
* must use HTTP
* easy backup strategy

!SLIDE incremental bullets

# Tokyo Tyrant #

* Network accessible Key-Value store
* single file DB
* values can be compressed
* Has a RESTful interface
* built in replication 

!SLIDE incremental bullets

# How we use Tyrants #

* cluster them (~250M keys / tyrant, bnum=1000000000)
* compressed values ( opts=ld )
* write once rule ( 'putkeep' mode )
* global keyspace (across all tyrants)
* partitioned keyspace ( somewhat like consistent hashing )

!SLIDE center
# 2x Physical Server #
![tt-slice/tt-slice.png](tt-slice/tt-slice.png)

!SLIDE incremental bullets
# How do you manage all those tyrants? #

* gem install tyrantmanager
* <http://github.com/copiousfreetime/tyrantmanager>
