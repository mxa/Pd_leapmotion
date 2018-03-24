#Pd_leapmotion
=============

Pure Data external for the leap motion controller by [Chikashi Miyama](https://github.com/chikashimiyama/Pd_leapmotion). Binary and [instructions for OS X](http://puredatajapan.info/?page_id=1514)

Modifications by [Jakub Valtar](https://github.com/JakubValtar/Pd_leapmotion)

Following instructions for Linux 64bit adapted from [Jordi Sala Serra](http://musa.poperbu.net/index.php/tecnologia-seccions-30/-puredata-seccions-45/129-installing-leapmotion-puredata-external-on-linux)

1. Download and install [Flext](https://github.com/grrrr/flext) (e.g. in directory /path/to/flext)
2. Download and unpack [LeapMotion SDK for Linux](https://developer.leapmotion.com/downloads) (e.g. in directory /path/to/LeapSDK)
3. Download and unpack the source of the object: (this github repository at https://github.com/mxa/Pd_leapmotion) (e.g in directory /path/to/Pd_leapmotion).
4. Modify the package.txt file in your Pd_leapmotion directory (the example is for a 64bit system)
5. From the Pd_leapmotion directory, compile the code using flext:

  `$cd /path/to/Pd_leapmotion`
  
  `$ bash ../flext/build.sh pd gcc`
  
  `$ bash ../flext/build.sh pd gcc install`

  If the last command fails (e.g: permissions), copy  leapmotion.pd_linux file (created in flext release-single directory) to extra    directory of PureData (e.g. /usr/lib/pd/extra

6. Finally, we can use this object. We need to preload libleap if we don't have it installed, so we need to execute:

  `$ LD_PRELOAD=/path/to/LeapSDK/lib/x64/libLeap.so pd`

7. To test it, make sure the Leap motion is running (run the visualizer tool) then open Pd and the `leapmotion-help.pd` patch
