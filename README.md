# The Medical Physicist's Guide to 3D Printing

> This was originally created for the AAPM Spring Clinical 2022 meeting, but the content is evergreen.

3D printing is a hugely powerful tool that is helpful in a variety of contexts, both personally and professionally. 
Here we present a zero-to-hero guide to get you up and running as quickly as possible.

### Get a Printer

There are a lot of 3D printers to choose from. Specifically, I'm only addressing Fused-Deposition Modeling (FDM) printing; there are numerous different methods of 3D printing. 
I describe here the typical, consumer-level method that extrudes plastic. 
The two that I can recommend are the [Ender 3](https://www.amazon.com/Comgrow-Creality-Ender-Aluminum-220x220x250mm/dp/B07BR3F9N6/ref=sr_1_3?crid=PO81S8XN0YT2&keywords=ender+3&qid=1647898347&sprefix=ender+3%2Caps%2C155&sr=8-3) (there is an original, Pro, and V2; any of them work) and the [Prusa MK3S](https://www.prusa3d.com/product/original-prusa-i3-mk3s-3d-printer-3/). 
The Ender is a low-budget (~$100-$300) entry-level printer. However, it's quite capable. Just be prepared to put some work in; it's got "good bones". The Prusa MK3S is closer to a turn-key solution. 
It has guided wizards and can come pre-assembled. Choose this if you want the results and don't care about the how. You don't have to pick one of these but I can recommend both. 
Generally, you'll want to pick a printer that satisfies these conditions:
  * **Is popular**. This is because the printer will have solutions to problems encountered vs a one-off from a no-name company. A printer is usually popular if it's 1) cheap and/or 2) has good customer support.
  * **Has customer support**. See above. In a professional context you want either: a) a clinical person who can become knowledgeable about 3D printing or b) good customer support.
  * **Will print the materials you need to**. See below about filaments. If you're printing simple models that will not be in heavy-duty usage, an open-frame printer without an enclosure is fine as the temperatures required for simpler filaments is lower.
    If you want to do very large items or print with difficult materials that require a high temperature (250C+), you may want to either pick a printer that focuses on that or buy an enclosure for an open-frame printer as it regulates the ambient air around the printer. 
    FFIW, I use an open-frame printer and only with the most difficult of models do I run into issues.
  
TL;DR: Get a Prusa if you want turn-key. Get an Ender or clone if you're interested in the craft and don't mind fixing it when it breaks. For 95% of you, I'd suggest a Prusa.

### Choose your filament(s)

Again, we're only talking about FDM printing. For this, the common materials are PLA, PLA+, PETG, Nylon, TPU, and Polycarbonate. Here is a breakdown: 

| Material/Characteristic | PLA          | PLA+        | PETG                  | Nylon        | TPU      | Polycarbonate |
|-------------------------|--------------|-------------|-----------------------|--------------|----------|---------------|
| Cost                    | $            | $           | $                     | $$           | $$       | $$$           |
| Ease of use             | ****         | ****        | ***                   | **           | **       | *             |
| Temperature resistance  | *            | **          | ***                   | ****         | ***      | ****          |
| Notes                   | Best starter | All-rounder | Great temp resistance | Very durable | Flexible | Ironman-tier  |

For more detailed info and comparison, see [this chart](https://www.help.prusa3d.com/en/materials?msclkid=fcf9ebf6a96011ec9441a8a469e56502). 

The thing to be aware of is your end use case and the conditions the part will be in. If the usage conditions are high-temperature (65C+), PETG and Nylon are preferable. If durability is key, Nylon or Polycarbonate (PC) are best. If it's just to keep two 
parts together or you want to test mechanical fit first on the cheap, use PLA. If flexibility is key (like a breast bolus), use TPU. If you don't know what to use, use PLA or 
PLA+. The "+" in PLA is not standardized and is specific to each company. Generally, this can mean increased temperature resistance or ductility. 

| Material/Characteristic | PLA   | PLA+  | PETG | Nylon | TPU       | Polycarbonate |
|-------------------------|-------|-------|------|-------|-----------|---------------|
| Temperature resistance  | poor  | poor  | good | great | great     | excellent     |
| Tensile strength        | great | good  | good | great | good      | excellent     |
| Ductility               | poor  | okay  | okay | great | excellent | poor          |
| Rigidity                | great | great | good | good  | poor      | excellent     |

You might ask, "Why not print everything in Nylon or TPU?" Because it's hard to print. Only use it after you've done 100 models in PLA.

You can get filament on Amazon or other major retailers. There are also 3D printing sites that sell specialized filament.

TL;DR: Use PLA as your first filament and for basic prints. Branch out to other filaments later and as needed based on the desired properties.

### Creating/Getting models

* **Finding a model**: You can find literally millions of designs for free on sites such as [Thingiverse](https://www.thingiverse.com/) or [PrusaPrinters](https://www.prusaprinters.org/prints). This works well for items lots of people use, but it's uncommon to find things a physicist may want or need given the audience size. Still, it's always preferable to do a search before creating your own model to save time if you can. 
* **Creating a model**: Eventually, you'll need to create your own model of something. There are lots of free resources on this. The two I can recommend are [TinkerCAD](https://www.tinkercad.com/) and [Fusion360](https://www.autodesk.com/products/fusion-360/overview). TinkerCAD can do 80% of what you are likely to need and is easy to use. 
  Fusion360 is professional CAD software and can do everything you could *ever* want to do. However, it's not free for commercial use. There are resources on how to learn both with a simple Google search.

In the 3D printing community, it is tradition to print out a ["Benchy"](https://www.prusaprinters.org/prints/3161-3d-benchy) as your first print. 
I would suggest downloading models first to get the rest of the printing process down before creating your own. When you realize the strengths and weaknesses of 3D printing you can design your model with this in mind.

### Slicing

"Slicing" is the process of converting the models we downloaded or created above from 3D geometrical concepts to instructions the 3D printer will understand in order to create the model.
This is the simplest step but still takes a knack to get it right all the time. The two most common slicers are [Cura](https://ultimaker.com/software/ultimaker-cura) and [PrusaSlicer](https://www.prusa3d.com/page/prusaslicer_424/). 
They'll both do what you need and have plenty of advanced options. Honestly, it's the dealers choice. If you go with a Prusa printer, PrusaSlicer works well with it, but you're more than free to use Cura with it too.

The most common parameters to be aware of when slicing are:

* **Print orientation**: Because the filament is laid down one layer on top of the other, it makes sense that if there *isn't* a layer underneath
  (such as an overhang) then the filament doesn't have anything to sit on. There are ways around this using "supports", but if you can choose a better orientation that's by far the easiest solution.
* **Wall thickness**: This defines how thick the parts are at the edges. The more walls the stronger the part.
* **Infill %**: 3D printed parts are not solid, nor should they be. Infill is the pattern and density of the inside of the part. This can be chosen based on desired strength or just for aesthetics. 
  Higher % will yield stronger parts, but wall thickness should be preferred over infill % for strength.

There are hundreds of other levers to pull in the slicer, but in the vast majority of cases the default is just fine.

At the end of this process you will have a G-code file (*.gcode) that contains instructions for your printer to follow.

### Printing

The part you've been waiting for! Printing the model is very satisfying but can also be frustrating when things don't go right.
To actually print the part you'll typically save the G-code file to an SD card or use monitoring software such as [OctoPrint](https://octoprint.org/).

The most common issues at this stage is when doing your first few prints. After working these out, you typically won't have
any problems, or you'll know how to fix them easily. 

* **Bed leveling/tramming**: This refers to the process of making the plane of the bed perfectly offset from the hotend. 
  3D printers are mechanical beings, and as such have mechanical tolerances and play in movement. Out of the box, 
  your bed may not be aligned perfectly. The process of bed leveling is either pretty easy if you have something like 
  a Prusa, or more involved with an Ender 3. Google and Youtube are helpful here as it can depend on your printer model.
* **Z-offset**: Z-offset is the space between the height value that the hotend calls "0" and the actual surface of the bed.
  This value should be about 0.2mm, which is the typical height of a layer. Printers like Prusa has wizards to guide you 
  through this process. Cheaper alternatives are more manual. Either way, the z-offset is important because if the 
  first layer isn't right the rest of your print may fail. Again, Goole and Youtube are helpful as it depends on the 
  printer as well as the bed surface. Some surfaces are smooth and others have a rough texture (for more grip).

### Good luck

3D printing is a very rewarding experience and is an extremely powerful tool to have in your toolbelt.
