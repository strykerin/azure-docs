---
title: Limitations
description: Code limitations for SDK features
author: erscorms
ms.author: erscor
ms.date: 02/11/2020
ms.topic: reference
---

# Limitations

A number of features have size, count, or other limitations.

## Azure Frontend

* Total AzureFrontend instances per process: 16.
* Total AzureSession instances per AzureFrontend: 16.

## Objects

* Total allowable objects of a single type (Entity, CutPlaneComponent, etc.): 16,777,215.
* Total allowable active cut planes: 8.

## Geometry

* **Animation:** Animations are limited to animating individual transforms of game objects. Skeletal animations with skinning or vertex animations are not supported. Animation tracks from the source asset file are not preserved. Instead, object transform animations have to be driven by client code.
* **Custom shaders:** Authoring of custom shaders is not supported. Only built-in [Color materials](../overview/features/color-materials.md) or [PBR materials](../overview/features/pbr-materials.md) can be used.
* **Maximum number of distinct materials** in an asset: 65,535. For more information about automatic material count reduction, see the [material de-duplication](../how-tos/conversion/configure-model-conversion.md#material-de-duplication) chapter.
* **Maximum dimension of a single texture**: 16,384 x 16,384. Larger source textures will be reduced in size by the conversion process.

### Overall number of polygons

The allowable number of polygons for all loaded models depends on the size of the VM as passed to [the session management REST API](../how-tos/session-rest-api.md#create-a-session):

| Server size | Maximum number of polygons |
|:--------|:------------------|
|standard| 20 million |
|premium| no limit |

For detailed information on this limitation, see the [server size](../reference/vm-sizes.md) chapter.

## Platform limitations

**Windows 10 desktop**

* Win32/x64 is the only supported Win32 platform. Win32/x86 is not supported.

**HoloLens 2**

* The [render from PV camera](https://docs.microsoft.com/windows/mixed-reality/mixed-reality-capture-for-developers#render-from-the-pv-camera-opt-in) feature is not supported.
