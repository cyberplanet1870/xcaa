# Mesh Guide
Written by litterbug1971

---

We use meshes for field logos. Meshes are also often used throughout stadiums, although decals can be used as well. This is a tutorial on how I make mesh logos, using Tulane as an example.
Everyone does things a little differently, and you will find something that works for you, but this is my method. A few notes important notes before we begin:
- Set CanCollide to false for field meshes
- Make meshes be 0.1 studs thick
- Separate mesh layers by 0.002 studs (if using a layered approach)
- Use RGB color (204, 215, 194) for white field logos as this will match the field lines
- If you need to add outlines to logos or text, square off the corners

---

### Required Software 
I will be using these programs. There may be other alternatives but they will not be covered in this tutorial.
- Image editing software such as [paint.net](https://getpaint.net/download.html)
- Vector graphics software such as [Inkscape](https://inkscape.org/)
- 3D modeling software such as [Blender](https://www.blender.org/download/)
- ROBLOX Studio

---

### Logo Finding/Editing

First, find an updated picture of the field:

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/32ea2c37-a6ab-4e47-81f7-13e871f0e3be)

Next, find pictures of the logos you need to make. https://www.sportslogos.net/ is a good site if you can't find anything. I got this off Google Images:

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/ca627201-2b76-454a-b447-a685515ed8f1)

Next, edit the image to your needs. Remove any trademarks/backgrounds. If you look closely at the midfield logo, there is a blue outline outside of the black outline that is missing in our image.
I added the outline in paint.net and squared off the corners and got this:

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/70711414-1260-4387-a86f-7f899749d068)

---

### Logo Layering

Now, meshes on roblox can only be one color, so we will need a separate mesh for each color of the logo: green, blue, black, and white. 

This is where I differ from many other developers. Lots of people simply separate the image into its different colors and put them all on the same layer, 
which works fine, but I prefer to stack the layers as it looks cleaner in my opinion, keeps triangle count low, and honestly it's just the way I learned how to do it.
If you are unsure what I mean by this, scroll down a bit to where I show the separated layers in-game and you will understand.

To layer meshes, imagine separating the image above into layers moving from outside inwards. Blue is the outermost color, so it would be on the bottom layer. 
Then comes black, then green and white (which do not touch, so they could be on the same height layer). In summary:
- Top layer(s): Green/White
- Middle: Black
- Bottom: Blue

Now, split the image up into its layers. If you are doing a stacked layer approach, fill in the transparent parts of the bottom layers that are covered by above layers.

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/2410031e-db20-45d1-9da3-2eed00423361)
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/f9820857-f0a9-4df6-a863-319e0980804a)
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/43ad04b7-0f36-4064-82bd-f1f6605ee621)
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/ddca8845-fbfa-4d70-99de-d395aa9c1652)

Next, color each layer black. This will be necessary for the next step. Save each layer as a .png file.

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/aea3f899-7d50-4577-b254-7fc7247a92bc)
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/46d77e03-ae54-48af-bc0e-afb326c13336)
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/ed09724b-b19f-44fa-acc4-26e2d0355a5e)
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/efa4a266-3548-4909-8acc-72c11363cfac)

---

### Inkscape

Import your black .png files to Inkscape. I will only show this for the blue layer but it works the same for everything. Click on the colored part of the imported image to select it. Then go to Path->Trace Bitmap and select a single scan using brightness cutoff. Finally, press apply.

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/f9e5e9b3-f413-4edf-b5e7-5861b46d0bc1)

Next, go to File->Export and export the selection as a .svg file. You can use File->Save As but sometimes the image gets cut off if it exceeds the bounds of the document page shown in the workspace (as is the case here). You can open the .svg file in a browser to see if it saved correctly. Repeat this for all of your layers.

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/eeec70a1-8c1b-40b2-b69d-d0b3303fd67b)

---

### Blender

Next, open up Blender. Go to File->Import->Scalable Vector Graphics (.svg) and import your .svg file. You may have to zoom in but you should see a flat version of your layer.

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/7c6371c5-7469-408e-ba04-4900a41b626d)

Select your object, then hit the icon that looks like a green curve. Go to the Geometery tab and set Extrude to 0.03m.

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/ccc5889b-ac5f-4529-a842-cf625f57fefa)

Next, we need to check the triangle count since roblox has a limit of 5000 triangles for meshes. Blender does not show you triangle count by default so you can enable it by presing the icon that looks like 2 circles and checking the box that says Statistics.

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/9a805097-7639-46ba-be05-6a81ee702f88)

This mesh is at 3516 triangles so we are good, but more complex meshes may exceed the limit of 5000. If this happens, click the wrench icon and add a Decimate modifier. For the Ratio property, enter 5000/the current triangle count. This will set the triangle count to 5000. It may end up only lowering the triangles to 5001 or so, in which case just lower the ratio by 0.001 until the count is below 5000.

Once the count is at or below 5000, save your mesh as a .fbx using File->Export->.fbx.

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/a911fa12-acb5-476a-9246-2476aa7a5c25)

---

### ROBLOX Studio

Now we need to import the mesh to studio. First, insert a MeshPart into workspace. Make sure it has Anchored=true and CanCollide=false. Also set its material to grass and color your mesh. If your mesh is white, set it to RGB (204, 215, 194) as this will match the lines on the field. In the Properties window, you will see the MeshId property. Click the file folder next to it and open up your .fbx file and click OK. If it prompts you to move/resize the mesh using location data, click no. You will see your mesh get imported as a thick ass shape:

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/af9f4eb1-dcbc-4a71-ad83-25e17818da4d)

Repeat for the rest of your layers. Once they are all imported, set the y-size of each to 0.1. Separate the layers by 0.002 studs in the y-direction and position them as needed. Here you can better see how the layering works. The green and white layers are not touching at all so they can be on the same y-level.

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/e673fe37-408c-45f1-810c-282911016baf)
![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/724aeaff-1a40-4fb8-93c8-5d33c10a4551)

Now, if you are using the field size guide and don't have the actual field model, you can move on at this point and someone else will size and position the meshes. However, if you have the field model you should resize/reposition the meshes now. Yard lines are at y=0.952, so the bottommost layer of your meshes should be at y=0.954 (or y=0.952 if in endzone). Be sure to set the thickness of the meshes back to 0.1 after you resize them.

![image](https://github.com/cyberplanet1870/xcaa/assets/123999017/f66100b6-8879-4fac-92a9-04ace88ac2c0)

Now repeat for the rest of your logos and you are golden. We already have conference logos made, so don't worry about those.

---

### Related Links

- [Building Guide](https://github.com/cyberplanet1870/xcaa/blob/main/building_guide.md)

