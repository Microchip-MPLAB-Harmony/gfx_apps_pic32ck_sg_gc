---
parent: Example Applications
title: Legato Adventure
nav_order: 2
---

# Legato Adventure

![](./../../images/legato_adventure.png)

This application demonstrates parallax and sprite animation capabilities using the graphics library. The application first launches a splash screen highlighting basic motion capability supported by the graphics library then transistions to the main screen.

When running the application, the user can interface with it via capacitive single-fingered touch and swiping gestures. The primary mode is presented in a mobile-game like style. In addition, two other features demonstrated by this application includes the circular gauge widget and the ability to display updating text at a high update rate (showing the score count). The lamb sprite character is animated by rapidly blitting frames of the animation character with slight position changes.

|MPLABX Configuration|Board Configuration|
|:-------------------|:------------------|
|[legato\_adv\_ck\_cu\_wqvga.X](./firmware/legato_adv_ck_cu_wqvga.X/readme.md)|PIC32CK_GC Curiosity Ultra using LCC MCU DMA graphics controller to drive the [High-Performance WQVGA Display Module with maXTouch® Technology](https://www.microchip.com/DevelopmentTools/ProductDetails/PartNO/AC320005-4)|