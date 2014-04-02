Detect_autoplay.js
=========

detect_autoplay.js does exactly what it sounds like it would - it detects autoplay support for HTML5 video elements. Hopefully we will someday live in a world where this is is not needed... but alas, as of now there is no cross-browser 
reliable way to detect HTML5 video autoplay support using just the DOM events. 

The plugin needs no framework (i.e. jQuery free) but won't get in the way if you are using one.

Usage
----
just add the plugin before your dependant scripts (i.e. anything that needs to know if autoplay is supported).
    
    <script type="text/javascript" src="path_to_file/detect_autoplay.js"></script>
from here the global variable **"autoplay"**  will be set as a boolean (*true* if autoplay is supported, *false* if not).

so for example if I was using jQuery and only wanted to show the video *#myvideo* if I know it will autoplay, I would do

    if(autoplay){                   //if autoplay is supported 
        $('#myvideo').show();       //show the video
    }
    
    
Settings
----
If you go into the plugin you will see there is a timer variable **"acceptable_delay"**, with a default setting of 100ms. Depending on connection speed and device processing power it might take the browser more than 100ms to start playing the tiny test video. I find it is usually a good idea to treat this case the same as no autoplay support - becuase if it takes the device longer than 100ms to start playing what kind of user experience will the real video provide? - but you may disagree. You can change this setting to give the browser more time (up to about 4.5 seconds, after that you end up racing the video). To do this simply edit 
    
    detect_autoplay(800);           //in this case we made the delay 800ms


That's it. Hope this helps a few of you create great new things on the web!

License
----

The MIT License (MIT)

Copyright (c) 2014 Knox Modern Media

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.


