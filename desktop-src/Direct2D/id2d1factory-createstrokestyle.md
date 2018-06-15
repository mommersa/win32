---
title: ID2D1Factory CreateStrokeStyle methods
description: Creates an ID2D1StrokeStyle that describes start cap, dash pattern, and other features of a stroke.
ms.assetid: cc7bd68b-a6eb-4d05-b331-032ce80f375c
keywords:
- CreateStrokeStyle methods Direct2D
topic_type:
- apiref
api_location:
- D2d1.dll
api_type:
- DllExport
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# ID2D1Factory::CreateStrokeStyle methods

Creates an [**ID2D1StrokeStyle**](https://msdn.microsoft.com/en-us/library/Dd372217(v=VS.85).aspx) that describes start cap, dash pattern, and other features of a stroke.

### Overload list



| Method                                                                                                                                                                                                  | Description                                                                                                                                |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------|
| [**CreateStrokeStyle(D2D1\_STROKE\_STYLE\_PROPERTIES&, FLOAT\*, UINT, ID2D1StrokeStyle\*\*)**](https://msdn.microsoft.com/en-us/library/Dd371301(v=VS.85).aspx)  | Creates an [**ID2D1StrokeStyle**](https://msdn.microsoft.com/en-us/library/Dd372217(v=VS.85).aspx) that describes start cap, dash pattern, and other features of a stroke.<br/> |
| [**CreateStrokeStyle(D2D1\_STROKE\_STYLE\_PROPERTIES\*, FLOAT\*, UINT, ID2D1StrokeStyle\*\*)**](https://msdn.microsoft.com/en-us/library/Dd371298(v=VS.85).aspx) | Creates an [**ID2D1StrokeStyle**](https://msdn.microsoft.com/en-us/library/Dd372217(v=VS.85).aspx) that describes start cap, dash pattern, and other features of a stroke.<br/> |



## Examples

The following example creates a stroke that uses a custom dash pattern.


```C++
// Dash array for dashStyle D2D1_DASH_STYLE_CUSTOM
float dashes[] = {1.0f, 2.0f, 2.0f, 3.0f, 2.0f, 2.0f};

// Stroke Style with Dash Style -- Custom
if (SUCCEEDED(hr))
{
    hr = m_pD2DFactory->CreateStrokeStyle(
        D2D1::StrokeStyleProperties(
            D2D1_CAP_STYLE_FLAT,
            D2D1_CAP_STYLE_FLAT,
            D2D1_CAP_STYLE_ROUND,
            D2D1_LINE_JOIN_MITER,
            10.0f,
            D2D1_DASH_STYLE_CUSTOM,
            0.0f),
        dashes,
        ARRAYSIZE(dashes),
        &amp;m_pStrokeStyleCustomOffsetZero
        );
}
```



The next example uses the stroke style when drawing a line.


```C++
m_pRenderTarget->DrawLine(
    D2D1::Point2F(0, 310),
    D2D1::Point2F(200, 310),
    m_pCornflowerBlueBrush,
    10.0f,
    m_pStrokeStyleCustomOffsetZero
    );
```



## Requirements



|                    |                                                                                     |
|--------------------|-------------------------------------------------------------------------------------|
| Library<br/> | <dl> <dt>D2d1.lib</dt> </dl> |
| DLL<br/>     | <dl> <dt>D2d1.dll</dt> </dl> |



## See also

<dl> <dt>

[**ID2D1Factory**](https://msdn.microsoft.com/en-us/library/Dd371246(v=VS.85).aspx)
</dt> </dl>

 

 




