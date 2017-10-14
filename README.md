Pd_leapmotion
=============

Pd external for leap motion by Chikashi Myiama https://github.com/chikashimiyama/Pd_leapmotion 
with modifications by Jakub Valtar https://github.com/JakubValtar/Pd_leapmotion
Instructions adapted from http://musa.poperbu.net/index.php/tecnologia-seccions-30/-puredata-seccions-45/129-installing-leapmotion-puredata-external-on-linux

1 Download and install Flext: https://github.com/grrrr/flext (e.g. in directory /path/to/flext)

2 Download and unpack LeapMotion SDK for Linux: https://developer.leapmotion.com/downloads (e.g. in directory /path/to/LeapSDK)

3 Download and unpack the source of the object: (this) (e.g in directory /path/to/Pd_leapmotion).

4 Modity the package.txt file in your Pd_leapmotion directory (the example is for a 64bit system)

5 From Pd_leapmotion directory, compile the code using flext:

  $cd /path/to/Pd_leapmotion
  $ bash ../flext/build.sh pd gcc
  $ bash ../flext/build.sh pd gcc install

If the last command fails (e.g: permissions), copy  leapmotion.pd_linux file (created in flext release-single directory) to extra directory of PureData (e.g. /usr/lib/pd-extended/extra

6 Finally, we can use this object. We need to preload libleap if we don't have it installed, so we need to execute:

  $LD_PRELOAD=/path/to/LeapSDK/lib/x64/libLeap.so pdextended

7 To test it, we can open leapmotion-help.pd patch
