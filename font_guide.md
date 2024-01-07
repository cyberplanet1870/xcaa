# Font Guide
Written by litterbug1971

---

We use custom fonts for jersey names and numbers. This is done by uploading decals of each font and storing a file with information about the font. 
Note that this is not a tutorial on designing fonts but rather on how to insert a new font into XCAA.

Detailed guides on each type of font are below, but a couple main points that apply to all fonts are:
- Resize image to max 1024 pixels wide before uploading (for numeric and alphabetical fonts)
- Use RGB (255, 255, 255) (white) for fonts so they can be recolored in-game
- Recommended to use Inkscape or Illustrator for font outlines instead of paint.net outline tool

---

### Numeric Fonts

Start off with a font you want to make. For this tutorial I will be making NFL Varsity Classic B:

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/15453b54-8cc6-490b-a476-b2e42e8432f7)

First, type your font out as 1234567890 as shown. Then, separate the font into different layers for the main color and any outline(s). 

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

Next, crop the image to the size of the largest layer (outermost outline). Then, recolor each layer to RGB (255, 255, 255) so that they can be recolored in game.
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



---

### Helmet Fonts

---

### Applying fonts to jerseys
Coming soon
note: mention the trick of using layer2 if you need a thicker font but no outline

---

### Related Tutorials

- [Jersey Guide](https://github.com/cyberplanet1870/xcaa/blob/main/jersey_guide.md)
