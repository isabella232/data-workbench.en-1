---
description: Data workbench Geography supports both latitude-longitude projections and Universal Transverse Mercator (UTM) projections for all terrain image layer sources.
solution: Analytics
title: Specifying Projection Information for Terrain Images
topic: Data workbench
uuid: 4a476192-e749-4187-b64e-9794f39b0019
exl-id: 400b9b59-f700-4b16-8549-fe93140cad1a
---
# Specifying Projection Information for Terrain Images{#specifying-projection-information-for-terrain-images}

Data workbench Geography supports both latitude-longitude projections and Universal Transverse Mercator (UTM) projections for all terrain image layer sources.

 Projection information is required for raw unprojected bitmaps and general images, unprojected. You can specify projection information for images with embedded projection information, though it is usually not required because the parameters of the projection are determined automatically from geodetic data embedded in the image itself. The following sections provide details about specifying these projection formats in the [!DNL Terrain Images.cfg] file.
