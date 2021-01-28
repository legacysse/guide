# Optimizing the Guide for your GPU VRAM.

By default, the guide uses a ton of VRAM. Even my 11GB 1080ti is at its limit, so the VRAM usage is a bottleneck for the LotD Plus guide. Depending on how much VRAM you have, that could be the case for whatever guide.

## The easy way

The easy way is to download a lower resolution version of mods that offer it. I am, however, not recommending that; I will explain why later.

If you have a slow internet speed or data cap, not much time, or just can't be bothered, this is your best option.

## The right way

Why am I calling that the right way? The answer is rather technical. 

Let's start with the nontechnical reason: Because you have the choice. If you resize the textures yourself, you can control where to do so down to the single texture or a folder full of them or a single mod or even the whole mod list if you want.

For the more technical reason, you have to understand Texture compression formats. In Skyrim, we use DDS textures. But DDS files are not equal. They can be uncompressed or compressed with BC1-7 / DXT1-5 compression.

Older formats like BC1 and BC3 compress by taking a 4x4 pixel block and giving each one 5/6/5 bits per channel. BC1 / DXT1 has one additional bit per pixel for the alpha channel, while BC3 has 8 bits per channel for the alpha channel (uncompressed). In addition to that, BC1 and BC3 only allow for two colors per 4x4 pixel block. Two more colors can be interpolated from those two colors getting us a total of four colors.

All in all, that results in blocky looking textures.

The new alternative is called BC7. BC7 is similar to BC3 in that it has the same compression factor. What makes it different is that each 4x4 pixel block has a dynamically allocated amount of bits per channel. This makes it a lot less blocky and visually lossless to most.

Another format to watch is BC4. That format is a single channel format, so it is useful for grayscale textures.

## How to do it

There are two tools you can use to resize textures. We will go with CAO (Cathedral Asset Optimizer). Ensure that you use the latest version since old versions had the texture resizing broken for dividing factors other than two.

1. Open CAO
2. Open the mod you want to resize with the Windows Explorer from MO. You can drag and drop the icon next to the path from Explorer into CAO, copy and paste the path into CAO or open the folder via CAO.
3. Under textures, enable Resizing, select by fixed size, and enter your target resolution. I would recommend 2048 in most cases.
4. Press run. CAO will now resize all mods that have a higher resolution than the target size. 

And that was it. Repeat it for all mods you want.

I would recommend starting with SRO (Skyrim Realistic Overhaul). That mod has many not so great looking textures that will free up your VRAM when resized.
