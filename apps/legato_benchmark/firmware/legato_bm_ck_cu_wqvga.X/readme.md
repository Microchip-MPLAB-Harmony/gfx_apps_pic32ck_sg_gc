
![](../../../../docs/images/mhgs.png) legato\_bm\_ck\_cu\_tm4301b.X

Defining the Architecture
-------------------------

![](../../../../images/PIC32CKGC_LCC_ARCH.png)

The application continuously uses the graphics library to render text, fill areas, and draw images to the screen. Once a layer is completely rendered to, the graphics library increments a layer swap counter. The application periodically (at 1 second intervals) samples the layer swap counter and calculates the difference from the previous sample. This difference is shown as the Frame Update Rate (Hz).

This configuration runs on the PIC32CK-GC Curiosity Ultra board an RGB565 GFX interface card and 4.3" WQVGA display. The Legato graphics library draws the updated sections of the frame to an internal scratch buffer. The scratch buffer is copied to the main frame buffer which is used to refresh the display through the Low-Cost Controller-less (LCC) driver.

User touch input on the display panel is received through the PCAP capacitive touch controller, which sends a notification to the Touch Input Driver. The Touch Input Driver reads the touch information over I2C and sends the touch event to the Graphics Library through the Input System Service.

### Demonstration Features

- Legato Graphics Library
- Low Cost Controller-less (LCC) display driver
- Time system service, timer-counter peripheral library and driver
- 16-bit RGB565 color depth support (65535 unique colors)
- SMC peripheral and driver
- I2C and touch controller driver
- RAW, RAW RLE images


Creating the Project Graph
--------------------------

![](../../../../images/pic32ck_cu_wqvga_bm_pg.png)

The Project Graph diagram shows the Harmony components that are included in this application. Lines between components are drawn to satisfy components that depend on a capability that another component provides.

Adding the **PIC32CK_GC Curiosity Ultra BSP** and **Legato Graphics w/ PDA TM4301B Display** Graphics Template component into the project graph will automatically add the components needed for a graphics project and resolve their dependencies. It will also configure the pins needed to drive the external peripherals like the display and the touch controller.

Building the Application
------------------------

The parent directory for this application is gfx/apps/legato\_benchmark. To build this application, use MPLAB X IDE to open the gfx/apps/legato\_benchmark/firmware/legato\_bm\_ck\_cu\_wqvga.X project file.

The following table lists configuration properties:

| Project Name  | BSP Used |Graphics Template Used | Description |
|---------------| ---------|---------------| ---------|
| legato_bm_ck_cu_wqvga.X |PIC32CK-GC Curiosity Ultra| Legato Graphics w/ PDA TM4301B Display | Legato GFX on PIC32CK-GC Curiosity Ultra board with PDA TM4301B 480x272 (WQVGA) Display  |

> \*\*\_NOTE:\_\*\* This application may contain custom code that is marked by the comments // START OF CUSTOM CODE ... and // END OF CUSTOM CODE. When using the MPLAB Harmony Configurator to regenerate the application code, use the "ALL" merging strategy and do not remove or replace the custom code.

Configuring the Hardware
------------------------

The final setup should be:

![](../../../../images/pic32_ck_cu_wqvga_config.png)

Configuring the 4.3-inch WQVGA Display requires disconnecting the ribbon cable that connects the display to the interposer board.

![](../../../../images/e70_xu_tm4301b_conf2.png)

First, release the ribbon cable from the interposer board. Next, release the black clamp on the connector and turn the display over. Finally, insert the ribbon cable into connector and close the clamp.

![](../../../../images/e70_xu_tm4301b_conf3.png)


The board can be debug via the on-board EDBG via the **Debug USB** port, or by using the ICE4 Debugger and the ICE4 Cortex-M Trace Adapter Board.

Running the Demonstration
-------------------------

On start-up, the application will display a splash screen.

After the splash-screen completes, the String Update benchmark screen is shown. In this screen, a counter is incremented at every application cycle. The screen demonstrates the rate at which the graphics library renders a string on the screen. This involves a fill operation that clears the background, lookup of the glyphs from the string library, and the drawing of the glyphs on the frame buffer.

![](../../../../images/legato_bm_wqvga_run1.png)

The **Frame Update (Hz)** field shows the current or instantaneous rate at which the graphics library updates the label widget that shows the counter value. Touching the Frame Update value switches between the current value (curr) and the average (avg) value across 10 samples.

Touching the + and - buttons increases and decreases the size of the string, respectively.

Touching the **Next** button switches to the Motion and Fill benchmark screen. In this screen, squares are showing moving across the screen. The Frame Update value is the rate at which the graphics library is able to render all the squares on the screen at their new positions. This involves a fill operation of the background color at the old location of the squares and a fill of the square/'s colors at the new position

![](../../../../images/legato_bm_wqvga_run2.png)

The number and size of the squares can be increased and decreased using the + and - buttons. If the maximum or minimum size is reached, touching + or -, respectively, will switch to a full screen fill of alternating colors.

Touching the **Next** button transitions to the Image Decode and Rendering screen. In this screen, two images of the same size are alternately rendered between application cycles. This involves a fill of the background color, decode and conversion of the image to the frame buffer format, and the drawing of the image to the frame buffer. The Frame Update value is the rate at which the graphics library is able to render an image on the screen.

The size of the images can be increased and decreased using the + and - buttons.

Touching the '<' and '>' buttons switches between the various image formats. The formats that are supported are RAW RLE 16-bit, RAW 16-bit and JPG 24-bit.

* * * * *

 
