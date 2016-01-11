# Introduction #

Processing library for capturing from PS3 Eye. You will need PS3 Eye drivers for Windows from AlexP.

# Details #

1. First install Win32 drivers for PS3 Eye camera. You can get latest version from AlexP blog - http://www.alexpopovich.com/blog/2008/10/02/sony-ps3eye-camera-directshow-capture-source-filter/

2. Copy **PS3EyeLib.dll** from you _/Program Files/AlexP/_ folder to _/windows/system32/_ or any other folder listed in you %PATH%.

3. Extract zip to **libraries** folder.

# Sample code #

import ru.cleoag.**;**

PS3Eye p;

PImage img;

int cameraWidth = 640;

int cameraHeight = 480;

int cameraRate = 60;

void setup(){
> size(640,480);

> p = new PS3Eye(this);

> p.start(cameraWidth,cameraHeight,cameraRate);

> img = createImage(cameraWidth,cameraHeight,RGB);

}
void draw(){

> background(0);

> p.update();

> p.imageCopy(img.pixels);

> img.updatePixels();

> image(img,0,0,width,height);

}

void stop(){

> p.stop();

}