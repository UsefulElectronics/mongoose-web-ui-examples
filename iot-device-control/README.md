[![Build Status](https://img.shields.io/badge/USEFUL%20ELECTRONICS-YOUTUBE-red)](https://www.youtube.com/user/wardzx1)

***
# Raspberry Pi Web Server Using Mongoose
***

### [Tutorial Link](https://youtu.be/hCiWYNtiOQQ) On [![Build Status](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/wardzx1)

Mongoose Wizard Web UI builder https://mongoose.ws/u/ywalm1 

Build a Fancy Web Server Without Front-End Coding! 🚀

In this tutorial, I’ll show you how to build a fully functional, great-looking web server even if you have no front-end coding experience!
We'll be using Mongoose Wizard to design a beautiful dashboard and deploy it on a Raspberry Pi to control your IoT devices from any smartphone, PC, or tablet. 📱💻

✅ UI design
✅ Backend handling
✅ Linux project compilation
✅ Step-by-step guidance

Whether you're a beginner or just looking for a faster way to create amazing IoT dashboards, this video will guide you through it all!


## Build and flash

**Step 1. Download generated project to your workstation**

Click on the "Generate" button to download the project to your workstation

**Step 2. Build and run the project**
- If your target IDE is CubeIDE, then start Cube IDE (use Cube 1.16.0 or later), then:
  1. Choose File / Import
  2. Choose "Existing Projects into Workspace", click Next,
  3. Click on "Directory", choose dir with generated files, click Finish
- If your target IDE is MCUXpresso, follow instructions for Cube IDE above
- If your target IDE is Arduino, open `wizard.ino` in the Arduino IDE
- If your target IDE is other - follow your IDE's guide

## Copying functionality to an existing firmware

In order to move this functionality to some existing firmware code, perform
the following steps:
1. Copy the `mongoose/` folder to your project
2. Edit the `mongoose/mongoose_config.h` file to adopt for your environment.
   See [Build Options](https://mongoose.ws/documentation/#build-options)
   for details
3. Add `mongoose/` to your include paths, and `mongoose/*.c` to source files.
   This depends on your IDE
4. Add the following to your code (e.g. to the `main()` function):

```c
#include "mongoose_glue.h"

...
mongoose_init();

// This blocks forever. Put this at the end of main(),
// or in a separate RTOS task. Give that task 8k stack space.
for (;;) {
  mongoose_poll();
}
```

For Ethernet hardware details, check [this tutorial](https://mongoose.ws/documentation/tutorials/hardware/)

## OTA firmware update

This feature uses binary images
- [Tutorial](https://mongoose.ws/documentation/tutorials/firmware-update/)

## Documentation and Tutorials

- [Tutorials](https://mongoose.ws/documentation/#tutorials)
- [Mongoose User Guide](https://mongoose.ws/documentation/)

![Circuit Diagram](https://github.com/UsefulElectronics/homebridge-devices/blob/main/diagram/rtsp%20server.png)
***
