# plane-alert
Monitor ADS-B records for occurrences of planes from a list

These are extremely minimalist install notes as this repository is mainly meant for my own backup purposes.
Since it was not designed to be very portable, simply use this as sample-code to implement your own / something better.
As per the license, acknowledgement of the source would be appreciated.

Based on BASH, runs on Raspberry Pi
In order to run this, the following dependencies must be installed:
- a working `dump1090` or `dump1090-fa` or `dump1090-mutability` installation
- Ted Sluis's `Socket3003` to collect the data from a dump1090 installation: https://github.com/tedsluis/dump1090.socket30003
- Install Twurl and configure Twurl for Raspberry Pi (or comment out the part of the script that sends tweets)
- You should manually install and start the `88-plane-alert.conf` file for `lighttpd`, or some other way make a web page available that points to the install's `html` directory
- I personally would make a directory named `/usr/share/plane-alert`, chown it to `pi:pi`, and recursively copy the repository there

# How to invoke
`/usr/share/plane-alert/plane-alert.sh <filename>`

The `<filename>` is a full path to one of the log files from Socket30003 - often `/tmp/dump1090-127_0_0_1-yymmdd.txt`
