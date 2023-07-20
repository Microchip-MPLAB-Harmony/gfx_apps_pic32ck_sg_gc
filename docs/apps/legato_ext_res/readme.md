---
parent: Example Applications
title: Legato External Resources
nav_order: 4
---

# Legato External Resources

![](./../../images/IntroScreen.png)

This project showcases how the Microchip Harmony Graphics Suite can be used to package images and font glyphs to be stored in external non-volatile memory, specifically a QSPI/SQI/NOR Flash.<br> The Microchip Graphics Composer plugin simplifies the process of generating binary files that need to be copied onto the external memory.

The **Setup** section allows the user to program the external SQI flash with ease via the Target USB port on the evaluation kit i.e. the MCU's USB Device Port.

The **Application** section demonstrates how the Legato Graphics Library can be setup to retrieve these external resources at runtime.

[legato\_x\_r\_ck\_cu\_wqvga.X](./firmware/legato_x_r_ck_cu_wqvga.X/readme.md) stores and retrieves resources stored on the on-board [SST26VF032BAT](https://www.microchip.com/en-us/product/SST26VF032BA) SQI flash memory.

![](./../../images/ExtResProcess.png)

This demonstration runs on:

|MPLABX Configuration|Board Configuration|
|:-------------------|:------------------|
|[legato\_x\_r\_ck\_cu\_wqvga.X](./firmware/legato_x_r_ck_cu_wqvga.X/readme.md)|PIC32CK-GC Curiosity Ultra Kit using LCC MCU DMA graphics controller to drive the [High-Performance WQVGA Display Module with maXTouch® Technology](https://www.microchip.com/DevelopmentTools/ProductDetails/PartNO/AC320005-4)|


 
