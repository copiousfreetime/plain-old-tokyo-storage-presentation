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
* global keyspace (across all tyrants)
* partitioned keyspace ( somewhat like consistent hashing )
* write once rule ( 'putkeep' mode )
* compressed values ( opts=ld )

