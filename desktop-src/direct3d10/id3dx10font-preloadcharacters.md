---
Description: Load a series of characters into video memory to improve the efficiency of rendering to the device.
ms.assetid: 935a6248-e6b7-4fce-aaa7-b7f0c94c1f79
title: ID3DX10Font::PreloadCharacters method
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# ID3DX10Font::PreloadCharacters method

Load a series of characters into video memory to improve the efficiency of rendering to the device.

## Syntax


```C++
HRESULT PreloadCharacters(
  [in] UINT First,
  [in] UINT Last
);
```



## Parameters

<dl> <dt>

*First* \[in\]
</dt> <dd>

Type: **[**UINT**](https://msdn.microsoft.com/windows/desktop/4553cafc-450e-4493-a4d4-cb6e2f274d46)**

ID of the first character to be loaded into video memory.

</dd> <dt>

*Last* \[in\]
</dt> <dd>

Type: **[**UINT**](https://msdn.microsoft.com/windows/desktop/4553cafc-450e-4493-a4d4-cb6e2f274d46)**

ID of the last character to be loaded into video memory.

</dd> </dl>

## Return value

Type: **[**HRESULT**](https://msdn.microsoft.com/windows/desktop/455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

If the method succeeds, the return value is S\_OK. If the method fails, the return value can be one of the following: D3DERR\_INVALIDCALL, D3DXERR\_INVALIDDATA.

## Remarks

This method generates textures containing glyphs that represent the input characters. The glyphs are drawn as a series of triangles.

Characters will not be rendered to the device; ID3DX10Font::DrawText must still be called to render the characters. However, by pre-loading characters into video memory, ID3DX10Font::DrawText will use substantially fewer CPU resources.

This method internally converts characters to glyphs using the GDI function [GetCharacterPlacement](http://msdn2.microsoft.com/en-us/library/ms534004.aspx).

## Requirements



|                    |                                                                                       |
|--------------------|---------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX10.h</dt> </dl>   |
| Library<br/> | <dl> <dt>D3DX10.lib</dt> </dl> |



## See also

<dl> <dt>

[ID3DX10Font](id3dx10font.md)
</dt> <dt>

[D3DX Interfaces](d3d10-graphics-reference-d3dx10-interfaces.md)
</dt> </dl>

 

 



