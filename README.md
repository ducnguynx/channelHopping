## Compile
gcc channel_hopping.c -o channel_hopping
## Run with 
sudo ./channel_hopping "interface"
# Adaptive feature
## Idea
After "RECALIBRATION_INTERVAL" the system will re-calibate the system by counting the received packages on every channel for 0.5s, so the total time for calibration is 7 seconds. So after calibartion, it will change the channel & dwell time according to the number of packages received, which translates to more packet - more percent dwell time (for an interval of TOTAL_INTERVAL time) 
