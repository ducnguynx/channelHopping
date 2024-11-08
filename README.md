## Compile
gcc channel_hopping.c -o channel_hopping
## Run with 
sudo ./channel_hopping "interface"
# Adaptive feature
## Idea
After "RECALIBRATION_INTERVAL" the system will re-calibate itself by counting the received packages on every channel for 0.5s, so the total time for calibration is 7 seconds. So after calibartion, it will change the channel & dwell time according to the number of packages received, which translates to more packet - more percent dwell time (for an interval of TOTAL_INTERVAL time) 
## HOTFIX Nov8 9:53PM
`pcap_loop()` wont respond when there are no traffic on the channel, fixed by using `pcap_dispatch()` as an alternative. For more details please refer to [pcap man page](https://linux.die.net/man/3/pcap_dispatch)
## Compile & Run
This program using libpcap-dev package, so in order to build & run. Run `sudo apt install libpcap-dev` in your terminal
`make all` to build
`sudo ./adaptive_channel_hopping <interface>` to run
