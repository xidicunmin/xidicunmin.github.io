---
title: halcon中Hobject转bitmap
date: 2021-08-15 11:35:00
updated: 
categories:
- halcon
tags:
- halcon
---
代码如下：

```csharp
/// <summary>
/// 灰度图像 HObject -> Bitmap
/// </summary>
public static Bitmap HObject2Bitmap(HObject ho)
{
    try
    {
        HTuple type, width, height, pointer;
        //HOperatorSet.AccessChannel(ho, out ho, 1);
        HOperatorSet.GetImagePointer1(ho, out pointer, out type, out width, out height);
        //himg.GetImagePointer1(out type, out width, out height);
        Bitmap bmp = new Bitmap(width.I, height.I, PixelFormat.Format8bppIndexed);
    ColorPalette pal = bmp.Palette;
    for (int i = 0; i <= 255; i++)
    {
        pal.Entries[i] = Color.FromArgb(255, i, i, i);
    }
    bmp.Palette = pal;
    BitmapData bitmapData = bmp.LockBits(new Rectangle(0, 0, width, height), ImageLockMode.WriteOnly, PixelFormat.Format8bppIndexed);
    int PixelSize = Bitmap.GetPixelFormatSize(bitmapData.PixelFormat) / 8;
    int stride = bitmapData.Stride;
    int ptr = bitmapData.Scan0.ToInt32();
    for (int i = 0; i < height; i++)
    {
        CopyMemory(ptr, pointer, width * PixelSize);
        pointer += width;
        ptr += bitmapData.Stride;
    }

    bmp.UnlockBits(bitmapData);
    return bmp;
}
catch (Exception exc)
{
    return null;
}
}
```