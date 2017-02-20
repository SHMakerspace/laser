# SH Makerspace Laser Cutter

## Fusion 360 DXF Post for Laser Cutter
In the `fusion360posts` folder is a post-processor that can be used with Fusion360's CAM module to create DXF files that can be directly imported into LaserWorks, with support for separating out the different "layers".

### Installation
Instructions vary by platform, but in Fusion360's Post Process window you can find the location for your personal user posts. 

For example, on Windows this will be `%APPDATA%\Autodesk\Fusion 360 CAM\Posts`, but you can also specify any folder you like.

Download the file `shm_laserworks_dxf.cps` from this repository, and put it in that folder.
You should now be able to select this "post configuration":

![Fusion360 Post](/fusion360posts/shm_laserworks/post.png)

### Configuring CAM
The intricacies of Fusion360 CAM are beyond this documentation, so if you have any difficulties, bring them to [the forum](https://forum.shmakerspace.org).
Basically, the process is:
1. Switch to the CAM module
2. Create a new "Setup"
3. Create a number of "Contours" 

The important part of the Setup is to make sure the X and Y axes are set to match the laser - depending on how you modelled your part, the Z axis might not be "up".

![Fusion360 Post](/fusion360posts/shm_laserworks/setup.png)

For each Contour, make sure the Type is set to `Laser cutting`, and the Kerf is set to match your laser (in our case 0.3mm). 

Because we'll be exporting a simple DXF, the feed rates are not normally used, so we've co-opted those to our cause. Set the rate to a number between `1` and  `20`, and that will determine the layer that this particular contour will appear as in LaserWorks.

![Fusion360 Post](/fusion360posts/shm_laserworks/contour.png)

You can add as many contours as you like, and if you give each one a different feed-rate, each will appear in LaserWorks with a different colour so you can configure the burn settings for each.

![Fusion360 Post](/fusion360posts/shm_laserworks/laserworks.png)

## SketchUp Models
This repository also holds the plans for the *Surrey & Hampshire Makerpspace* laser cutter table, and a model of the laser to use in making plans for the space.

![Laser Cutter](/models/renders/LaserAssembly.jpg)

![Bench](/models/renders/LaserBench0001.jpg)
