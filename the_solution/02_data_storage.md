!SLIDE incremental bullets transition=toss

# Part 1 - Message Storage System #

* must store 1 billion messages
* efficient use of disk space
* accessible via a "key"
* assessible via HTTP
* easy backup strategy

!SLIDE incremental bullets

# Tokyo Tyrant #

* Network accessible Key Value Store
* Has a RESTful interface
* built in replication 
* single file DB
* values can be compressed

!SLIDE incremental bullets

# How we use Tyrants #

* cluster them (~250M keys / tyrant)
* global keyspace (across all tyrants)
* partition keys to individual tyrants
* 'putkeep' storage
* compressed values

