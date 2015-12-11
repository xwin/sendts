# Kwikflix UDP send
## kwik-udp-send

### Features

* Sending ts file(s) as a ts udp stream

* If there is no files to send, it sends null packets

* Works with real-time process/threads priorities to provide stability of the stream

* Works with FIFO files

### Tested environments

* Debian Jessy

* Ubuntu 14.04 LTS

### Build

Just run make in the project directory

### Command-line options

* -i <address> - ip address to send packets

* -p <port> - port to send packets

* -b <bitrate> - bitrate of stream

* -d <path to diectory> - send all files from a directory, sorted my modified time, the directory is scanned in real-time, you can add files on fly

* -f <path to file> - send one file, you have to select either a file or a directory

* --ts_in_cache <number>, -s <number> - commons cache size

* --accumul_ts <number>, -a <number> - size of filled cache part

* --ttl <number>, -t <number> - set ttl

* --pri <number>, -P <number> - set the process/thread priority

* --ts_in_udp <number>, -u <number> - the number of ts packets in one udp packet

* -c - don't stop file reading if it read zero bytes, use it for FIFO files

* -m - print debugging messages on the screen

* -l <file name> - save debugging messages to a file 

###Examples

####Reading directory
sudo ./kwik_udp_send -d /ts -i 239.0.0.10 -p 1234 -l ./log --ts_in_cache 40000 --accumul_ts 20000 -b 2000320

####Reading FIFO file, generated by ffmpeg
sudo ./kwik_udp_send -f /ts/tst.ts -i 239.0.0.10 -p 1234 -l ./log --ts_in_cache 40000 --accumul_ts 20000 -b 2000320 -c

### Feedbacks and tickets

We will appreciate you feedbacks or any contribution to our app. So, create tickets and let's discuss.


