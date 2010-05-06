!SLIDE incremental bullets transition=toss

# Ruby Interfaces for Cabinet #

* Raw C Extension provided with TC
* [rufus-tokyo](http://github.com/jmettraux/rufus-tokyo)
* <i>FFI based, in maintenance mode</i>
* [Oklahoma Mixer](http://github.com/JEG2/oklahoma_mixer)
* <i>FFI based, this is what JEG2 has been up to</i>

!SLIDE incremental bullets

# Ruby Interfaces for Tyrant #

* Ruby implementation provided with TT
* [rufus-tokyo](http://github.com/jmettraux/rufus-tokyo)
* <i>FFI based, in maintenance mode</i>
* [ruby-tokyotyrant](http://github.com/actsasflinn/ruby-tokyotyrant)
* <i>Native C extension</i>
* Any Memcache Library

!SLIDE smaller code
    @@@ruby
    require 'oklahoma_mixer'       

    OklahomaMixer.open( 'rcrd.tch' ) do |db|
      lines = 0                    
      Dir.glob("/usr/share/dict/*").each do |word_file|

        basename = File.basename( word_file )
        next if basename == "README"
        next if File.symlink?( word_file )

        File.open( word_file ) do |f|
          f.each_with_index do |word, idx|
            lines += 1             

            db.store( word, "#{basename}:#{idx}", :keep )
            # or like a hash db[word] = "#{basename}:#{idx}" 

          end
        end
      end

      puts "stored #{db.size}, total #{lines}" 
      # => stored 312082, total 312614

    end
