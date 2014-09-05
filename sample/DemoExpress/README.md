## Introduction

This sample demostrates the basic useage of standard APIs that are supported by Crosswalk.
Please refer to the API spec details to https://crosswalk-project.org/#documentation/apis/web_apis

## Authors:

* Lin, Wanming <wanmingx.lin@intel.com>

## LICENSE

Copyright (c) 2014 Intel Corporation.  All rights reserved.
Except as noted, this software is licensed under BSD-3-Clause License.
Please see the LICENSE.BSD-3 file for the BSD-3-Clause License.

## Deploy DLNA server on tizen ivi device

  * Set up dlna server follow the steps:
  1. Modify rygel.conf on IVI device.
  $ cp /etc/rygel.conf /home/app/.config/

  - video-upload-folder=@VIDEOS@
  + video-upload-folder=/home/app/Videos

  - music-upload-folder=@MUSIC@
  + music-upload-folder=/home/app/Sounds

  - picture-upload-folder=@PICTURES@
  + picture-upload-folder=/home/app/Images

  # Allow upload of media files?
  - allow-upload=false
  + allow-upload=true

  # Allow deletion of media folders and files?
  - allow-deletion=false
  + allow-deletion=true

  strict-sharing=false
  - title=@REALNAME@'s media
  + title=iTracker

  [MediaExport]
  - enabled=false
  - title=@REALNAME@'s media
  + enabled=true
  + title=iMediaExport

  - uris=@MUSIC@;@VIDEOS@;@PICTURES@
  + uris=/home/app/Videos;/home/app/Sounds;/home/app/Images;
 
  enabled=true
  - title=My Media
  + title=iLMS

  enabled=true
  - title=Audio/Video playback on @HOSTNAME@
  + title=iPlaybin

  2. Create Videos, Sounds and Images directories in /home/app/ on IVI device.

  3. Add some media content to IVI device.
  * Copy media files to /home/app/Videos, /home/app/Sounds and /home/app/Images.

  4. Launch of services on IVI device.
  $ su - app
  $ rygel