
![](../../../../docs/images/mhgs.png) blank\_qs\_ck\_cu\_wqvga.X

Defining the Architecture
-------------------------

![](../../../../images/PIC32CKGC_LCC_blank_ARCH.png)

In this configuration, a 16-bit RGB565 frame buffer is stored in the internal SRAM. This configuration uses the Low Cost Controller-less (LCC) display driver to transfers the frame-buffer contents to the display.

User touch input on the display panel is received through the PCAP capacitive touch controller, which sends a notification to the Touch Input Driver. The Touch Input Driver reads the touch information over I2C and propogates the touch event through the Input System Service which is handled in the application code.

### Demonstration Features

-   Touch Event Handling
-   DMA System Service
-   Low-Cost Controllerless (LCC) graphics driver
-   16-bit RGB565 color depth support (65535 unique colors)
-   RAW image stored in internal flash

Creating the Project Graph
--------------------------

![](../../../../images/pic32_ck_gc_bqk_wqvga_ARCH.png)

The Project Graph diagram shows the Harmony components that are included in this application. Lines between components are drawn to satisfy components that depend on a capability that another component provides.

Adding the **PIC32CK_GC Curiosity Ultra BSP** and **Legato Graphics w/ PDA TM4301B Display** Graphics Template component into the project graph will automatically add the components needed for a graphics project and resolve their dependencies. It will also configure the pins needed to drive the external peripherals like the display and the touch controller. **Remove the Legato Component to complete the setup**.

Building the Application
------------------------

The parent directory for this application is gfx/apps/blank\_quickstart. To build this application, use MPLAB X IDE to open the gfx/apps/blank\_quickstart/firmware/blank\_qs\_ck\_cu\_wqvga.X project file.

The following table lists configuration properties:

The following table lists configuration properties:  

| Project Name  | BSP Used |Graphics Template Used | Description |
|---------------| ---------|---------------| ---------|
| blank\_qs\_ck\_cu\_wqvga.X |PIC32CK_GC Curiosity Ultra| Legato Graphics w/ PDA TM4301B Display | PIC32CK_GC Curiosity Ultra board with PDA TM4301B 480x272 (WQVGA) Display  |

> \*\*\_NOTE:\_\*\* This application may contain custom code that is marked by the comments // START OF CUSTOM CODE ... and // END OF CUSTOM CODE. When using the MPLAB Harmony Configurator to regenerate the application code, use the "ALL" merging strategy and do not remove or replace the custom code.


Configuring the Hardware
------------------------

The final setup should be:

![](../../../../images/pic32_ck_cu_wqvga_config.png)

Configuring the 4.3-inch WQVGA Display requires disconnecting the ribbon cable that connects the display to the interposer board.

![](../../../../images/e70_xu_tm4301b_conf2.png)

First, release the ribbon cable from the interposer board. Next, release the black clamp on the  connector and turn the display over. Finally, insert the ribbon cable into connector and close the clamp.

![](../../../../images/e70_xu_tm4301b_conf2.png)


The board can be debug via the on-board EDBG via the **Debug USB** port, or by using the ICE4 Debugger and the ICE4 Cortex-M Trace Adapter Board.

Running the Demonstration
-------------------------

Once the board is powered on, the application will run and show the following image on the display panel.

![](../../../../images/blank_quickstart.png)

* * * * *

 
