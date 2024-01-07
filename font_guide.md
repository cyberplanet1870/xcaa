# Font Guide
Written by litterbug1971

---

We use custom fonts for jersey names and numbers. This is done by uploading decals of each font and storing a file with information about the font. 
Note that this is not a tutorial on designing fonts but rather on how to insert a new font into XCAA.

Detailed guides on each type of font are below, but a couple main points that apply to all fonts are:
- Resize image to max 1024 pixels wide before uploading (only for numeric and alphabetical fonts)
- Use RGB (255, 255, 255) (white) for fonts so they can be recolored in-game
- Recommended to use Inkscape or Illustrator for font outlines instead of paint.net outline tool

Also be sure to check out our [font database](https://github.com/cyberplanet1870/xcaa/blob/main/font_database.md) to see if a font has already been created before making one.

---

### Numeric Fonts

Start off with a font you want to make. For this tutorial I will be making NFL Varsity Classic B:

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/15453b54-8cc6-490b-a476-b2e42e8432f7)

First, type your font out as 1234567890 as shown. You should use a large font size and canvas to get the highest level of detail. 
Then, separate the font into different layers for the main color and any outline(s) if they exist. 

<details>
  <summary>Side note on creating good outlines</summary>

### Outline Creation
If your font has outlines, I highly recommend using a vector image software
such as Inkscape or Adobe Illustrator to create the outline as a text stroke and then export each layer as a .png image. 
If you use the outline object tool in paint.net, you can end up with rounded corners. Even if you use the trick where you copy the original image layer
and make 8 outline layers using the arrow keys to position them, you can end up with outlines that are too thick on slanted edges like this:

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/0935fdaa-37b3-4d06-bb1a-016c83b453d1)

Now I am not a graphic designer by any means and you might have a better way of doing things, but using Inkscape is the best method I have found.

</details>

Next, crop the image to the size of the largest layer (outermost outline). Then, recolor each layer to RGB (255, 255, 255) and remove any backgrounds so that they can be recolored in game.
You can do this using the [Object2Colour plugin](https://forums.getpaint.net/topic/22500-red-ochre-plug-in-pack-v9-updated-30th-july-2014/#entry358375) in paint.net.
Finally, if your image is over 1024 pixels wide, you will need to resize it down to 1024. This is because Roblox automatically does this when uploading large images
and if your image is any wider then the next part will not work. Your final images should look like this:

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/09d697af-2a37-4568-a607-01b23eea489c)
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/dfccfd0c-ec68-46ff-ae80-7f5bc9714fd7)

Note that both of these images are the same size and the top layer (inner color) has some empty space around the edges.

Now, it is time to make the font file. Download the [font templates](https://github.com/cyberplanet1870/xcaa/blob/main/assets/font_templates.rbxm) and open the NumericalFontTemplate in Studio.

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/c8aed717-1676-4bcd-9ef4-a51b60ac9f95)

First, name the ModuleScript to whatever you want. I usually type the name of the font and if it is a numeric or helmet font I stick Numeric/Helmet at the end. 
For example, I named this VarsityClassicBNumeric. Also put this at the top of the file.

Next, upload your images and put the image IDs (NOT decal IDs) into the Layers table. Enter these in the order that they are layered top-to-bottom in paint.net.
For example, the inner text color layer is on top of the outline layer, so it comes first in the table. You can also add/remove any layers as needed.
Just don't leave any empty strings in this table (if the font only has one layer for example).

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/bca62e2d-8fc4-49ba-8384-8e746c1db031)

Next, set Size to the size of your image. Remember, the width should be less than or equal to 1024.
Now, set the position and width of each of the numbers. The first number is the position of the leftmost x-coordinate, and the second is the width of the number.
So, for #1, it is at position x=0 and is 64 studs wide, so you would enter (0, 64). #2 is at x=68 and is 102 studs wide so you would enter (68, 102) and so on.
Repeat this for all the numbers.

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/a9204b89-be42-40a9-a11f-f397a3a7406c)
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/8280b04f-fa21-4c3a-b70f-29e7a88da135)

---

### Alphabetical Fonts

Alphabetical fonts work the same as numeric fonts except you have 28 characters to make (A-Z, -, and .) instead of 10. Because of this, they take fucking forever and I only have a couple made
that I use for all the teams. I personally don't really care about getting these right so much as the numbers but if you want to make one go right ahead.

Since it's essentially the same process as making numeric fonts, I won't be repeating everything from above. To make an alphabetical font, just type out your font as (including the period):

ABCDEFGHIJKLMNOPQRSTUVWXYZ-.

I HIGHLY recommend using a large font size and canvas (3000+ pixels) since it will need to be resized down to 1024 and will lose more detail than numerical fonts as each individual character is smaller.
Then, repeat the same steps as the numeric font tutorial, using the AlphabeticalFontTemplate from the [font templates](https://github.com/cyberplanet1870/xcaa/blob/main/assets/font_templates.rbxm).

Here is Varsity Block A:

Original image (3921x276):
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/e65e4df4-9466-4b44-b214-be010d7b6516)

Resized image (1024x72):
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/4449f23b-13e0-4862-a8d6-aaddf2a8b67c)

Individual layers:
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/8c49e857-171d-42e9-987c-a945a5183754)
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/dad1d864-a09f-4687-a034-2ec661064140)

Font file:
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/6abaf724-4c0c-45a9-8a05-8770a4a2a1d1)

---

### Helmet Fonts

Some teams like Alabama have numbers on their helmets. These are a bit of a bitch since you have to upload 20 images (0-9 ones place and tens place), but you don't have to worry about resizing to 1024.
Note that we currently do not support outlines on helmet fonts using multiple layers. You can still have a font with an outline, but the outline has to be on the same layer as the text and you won't be able to recolor it in-game.

First, create a square image (any size, I recommend using a large image though). Now, you are going to need to create a separate layer for each number 0-9 for both the tens place and ones place.
Position the numbers so they are centered (horizontally at least, they can be a bit above center vertically) as this will be a decal that goes on the side of the helmet. 
I recommend having a positional guide like the 2 black boxes shown below to ensure that your numbers stay centered. The [.pdn file](https://github.com/cyberplanet1870/xcaa/blob/main/assets/Alabama%20Helmet%20Font.pdn)
for this font is available so you can better understand what I mean.

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/2514553b-585e-4bc8-b63a-e7a02faf8043)

Next, upload each layer as its own image. For example, the 21 above needs a separate image for the 2 (tens place) and 1 (ones place):

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/88bb515b-8a81-4bfb-9888-4ef5f6de7097)

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/c375a6cf-9320-4095-bf94-d6d1375df260)

Next, open the HelmetFontTemplate from the [font templates](https://github.com/cyberplanet1870/xcaa/blob/main/assets/font_templates.rbxm). Just insert all of your image IDs into each table and name the file to whatever you want.
Set the ShowLeadingZeroes flag to true if you want single digit numbers to appear with a zero in front of them ('9' becomes '09'). 

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/1f33316c-f899-4b4d-9afa-44c8bc4a8776)

---

### Applying fonts to jerseys
Coming soon. I hope to make a jersey creation place since there is currently no way to test the fonts unless you have full dev access.
For now, if you make a font file just send it to me (litterbug1971) and I will insert it.

note: mention the trick of using layer2 if you need a thicker font but no outline

---

### Related Links

- [Jersey Guide](https://github.com/cyberplanet1870/xcaa/blob/main/jersey_guide.md)
- [Font Database](https://github.com/cyberplanet1870/xcaa/blob/main/font_database.md)
