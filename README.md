# mp3-duplicate-finder

The find_mp3_duplicates PERL script is designed to do one thing: find duplicate audio files, based on the audio content, from two distinct directory trees. It was made to help merge two somewhat-overlapping music collections, but may be adapted for other useful purposes.

It uses the MP3::Info module to extract the audio portion of the file, and then generates an md5 hash of the audio portion. The output assumes that you want to keep the master intact, and remove files from the slave. The basic program flow is:

* Generate & store hashes from 1st (master) directory
* Generate hashes from 2nd (slave) directory and immediately compare to master
* For any duplicate hash:
 * Print duplicate to screen
 * Print duplicate to results text file
 * Print duplicate to results script

# Disclaimers

* It is inefficient: it uses a lot of memory to store your master data.
* It insecurely opens (and clobbers) your output files. Deal with it.
* Won't find the same song that was ripped on a different machine.
* Uses unix 'find' so it won't run on Windows. Deal with it.
* Only tested on OS X.
* Use at your own risk.

 That said, it, doesn't rely on file name or tag information, which is how most programs find duplicates.

Enjoy.


