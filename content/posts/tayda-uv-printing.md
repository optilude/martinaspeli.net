+++
title = 'Tayda enclosure UV printing for guitar pedals'
date = 2024-03-07T21:00:00Z
draft = true
+++

I have built many guitar effects pedals from [Jeds Peds](https://www.jedspeds.co.uk), who sell a bewildering array of PCB pedal kits, and has a great builder community on Facebook. The kits arrive by default with unpainted enclosures, which you can decorate yourself, and that's part of the fun. Most people use spray painting and home-printed waterslide decals for this, but after my first batch of pedals, I decided that painting is my least favourite part of the process. It requires a level of patience and consistency that I don't possess, is sensitive to temperature and humidiy, and makes a mess. And even with base coats, multiple colour coats, and clear top coats, my pedals all chip and ding too quickly.

There are better ways. Commercial enclosures will commonly be power-coated, which is more durable, and will have any designs printed on them directly, rather than applied via a decal. [Tayda Electronics](https://www.taydaelectronics.com) is an online electronics store from Thailand, which is popular with guitar pedal builders for supplying both components and hardware for DIY/hobby projects. And it sells both powder coating and design printing services. So for my most recent build, I decided to use this instead of painting and printing at home.

It's not _entirely_ obvious how it all works, though, so here is my attempt at documenting the process. I learned all of this form others, in particular [this tutorial from Patchyderm Pedals](https://www.pachydermpedals.com/tutorials/2020-12-27-angry-charles-tutorial/), [this forum thread from Steggo Studios](https://forum.pedalpcb.com/threads/steggo-studios-tayda-uv-printing-tutorial-part-1.15268/), and [this video series](https://youtu.be/iH_k_C3WFLU?si=40jGqZ2HyuiLko-G), as well as advice and examples from David Summers of the Jeds Peds forum.

The basic idea is as follows:

- Get the PCB and components you need. Tayda does sell some PCBs, and a good range of components, though in my case I got both from Jeds. (You want to order the PCB, components, and off-board components like jacks and switches, but not the "full kit" option that includes the enclosure.)

- Order the enclosure from Tayda, in the colour you want. It obviously needs to be big enough for the pedal you're making. Enclosure sizes have funny names like 125B (a common size used by Jeds Peds in their kits), 1590BB, etc. For example [here is the product page](https://www.taydaelectronics.com/hardware/enclosures/1590b-style-1.html) for 125B style enclosures in various colours. There are also some pre-drilled Tayda enclosures, but we will not be using those. Note down the Pantone colour name - it'll come in handy later when you work out your design.

- Order the [Enclosure Custom Drill service](https://www.taydaelectronics.com/hardware/enclosures/enclosure-custom-drill-service.html) from Tayda for the relevant enclosure type. For example, [this is the 125B drilling service](https://www.taydaelectronics.com/hardware/enclosures/enclosure-custom-drill-service/125b-custom-drill-enclosure-service.html). This lets you ask Tayda to drill the face (for knobs and switches) and top/sides (for jack and power sockets) for you. You will create a _custom drill template_ that will let you specify precisely where the holes go and how large they are.

- Order the [Enclosure UV Printing service](https://www.taydaelectronics.com/hardware/enclosures/enclosure-uv-printing-service.html) from Tayda. This page has a lot of detail of how the service works, and you must read it all the way through, though I'll also describe some of the pertinent points below. You basically order the relevant size of UV printing (like [this one for printing on the face of a 125B enclosure](https://www.taydaelectronics.com/hardware/enclosures/enclosure-uv-printing-service/125b-uv-printing-service.html)), and probably also the optional [gloss layer printing service](https://www.taydaelectronics.com/hardware/enclosures/enclosure-uv-printing-service/custom-uv-gloss-layer-service.html), which lets you overprint a layer of shiny or matte transparent ink, giving a better sheen and some extra protection.

- Create an account on the [Tayda Drill service](https://drill.taydakits.com/dashboard). This is a separate webapp by the same company. You _must_ use the same email address for the drill service account and the Tayda web store account, or you won't be able to link your order to the drill template.

- In the drill tool, there is a web interface for defining a drill template. You can find [existing ones that others have shared](https://forum.pedalpcb.com/forums/drilltemplates/) as a starting point, or define your own from scratch. Essentially, you place holes on a coordinate system (where 0,0 is the centre of the enclosure) and define how big each one should be (**Note:** You must add 0.2mm to whatever size you want to allow for the powder coat, which will stick to the insides of your hole and make it slightly smaller). A little while after you've placed your order on the main Tayda web shop, you'll be able to link the enclosure you've bought to a specific drill template.

- Create an appropriately formatted PDF that will be used for UV printing the design. The strong recommendation from Tayda is that you do this in Adobe Illustrator. The problem with that, is that Illustrator is expensive if you don't already have it. [Affinity Designer](https://affinity.serif.com/en-gb/designer/) is a popular alternative that is more reasonable. I used the iPad version for my design, which is available in the App Store. There are a lot of rules and nuances to getting the PDF right, and if it's not Tayda may at best send it back to you, and at worst print something that will look wrong. More on this below.

- Upload the UV printing PDF file in the Tayda drill tool and link it to your order.

- Wait patiently for a few weeks.

## Getting the drill template right

The Tayda drill template tool lets you pick an enclosure type (which must obviously match what you've bought, e.g. 125B), and then add up to 40 holes. In each, you enter a diameter in mm, and an X and Y position. Note that:

- You pick the side that the holes go on, where A is the face (typically for knobs and switches), B is the top, C is the left side, and E is the right side. So depending on whether you want your pedal to have top- or side-mounted jack and power sockets, you need to pick the right location.
- If you are getting the enclosure powder coated (or if you are going to paint it yourself later) you need to add 0.2mm to the size of each hole, because the powder coat will get inside it. They drill first and coat later!
- The X/Y position is based on a coordinate system where (0,0) is dead centre of the enclosure. So a position of (10,10) is 10mm to the right past the vertical mid line, and 10mm above the horizontal mid line.

You can also use the "line" option in the drill template tool to make non-circular cutouts, though I've not had a need for these.

Entering the template is relatively straightforward, but deciding the exact position of each hole might not be. This is where finding some examples might help, and the [PedalPCB forum](https://forum.pedalpcb.com/forums/drilltemplates/) contains a bunch. You need to be logged into the drill tool first, and then you can click one of the links to get a template someone else has shared pre-loaded into the editor. Save it as your own and it'll make a useful starting point.

Most of the Jeds pedals come with PCB-mounted pots and switches. What that means is that the pots and switches are soldered directly onto the PCB, not connected with short wires. This makes installing them into the enclosre easier, but it means you have to be very precise with where the holes for your pots (knobs) will go. If you wire in the components, they are more fiddly to install, but you have more freedom over exactly where they are positioned. Short, solid-core wires that have some rigidity to them are good for this type of job.

Another thing to think about is how much space there is inside the enclosure. A large PCB, with many pots and switches, will have less room for error, because you might end up with a pot getting in the way of a jack socket or a switch not fitting between two knobs. Careful measurement is the key, since the Tayda drill service has a long lead time. Unless you're confident, I'd recommend buying the PCB and controls first, building the guts of the pedal, and then checking your measurements. Or even ordering the Jeds pre-drilled enclosure and take measurements from it, even if you aren't using it.

## Getting the design PDF right

Before we get into some specifics, let's talk about some of the gotchas and quirks of making a design for UV printing.

1. The PDF must use CMYK colour space, not RGB.
2. The PDF must be the exact dimensions of the enclosure, in mm. The Tayda UV printing guide has the expected sizes and template files you can use. For 125B, for example, that is 62mm wide and 117mm tall.
3. Nothing can be placed outside the edges of the file, i.e. you need to delete or crop anything that goes off the side of your file.
4. _Everything_ in the design must be vector graphics, so:
  - You can add text with whatever font you want, but before exporting the file, you need to convert them to paths (or "curves", as Affinity will call them) which really just means each letter becomes a separate vector shape.
  - If you want to use clipart or bitmap images (like PNG, JPEG, or GIF files), you need to vectorise them first. This can be a little hit and miss, but [Vectorizer.com](https://vectorizer.com) seems to do a decent job of it for free. Simpler, cleaner designs will generally work better.
5. Your main design needs to live entirely in a single layer named "COLOR". You can use other layers during the design process, and this can be useful for previewing the design (e.g. to show the true background colour, the positions of knobs and switches, etc.), but you have to hide them before exporting so they are not in the main PDF.
6. Nothing can overlap in each of your exported layers. You need to flatten and modify vector shapes so that they don't. (This is to preserve colour representation, apparently.)
7. Most printers can't print white. The UV printer _can_ do so, but only in a special layer, which must sit beneath the "COLOR" layer and must be called "WHITE" . To tell the printer to do so, you don't actually submit something that will look white on your screen. Instead, you use a special "spot colour" called `RDG_WHITE` from a special "Roland" swatch, which looks gray but comes out white. (In CMYK, this colour is `(25, 25, 25, 25)`). If you want something to look white, you need to draw it in the "WHITE" layer and then ensure nothing in the "COLOR" layer obscures it.
8. You often need a white "base coat" underneath your actual design, even if the final colour isn't meant to be white. This is because a printer generally assumes it is printing on a white background. So if you are printing "light yellow", it deposits a little bit of yellow on top of the white, and if you are printing "dark yellow" it deposits a bit more. But if your powder coating is not white, this can turn out very different (blue + yellow = green, for example). The solution is to paint in white first on the "WHITE" layer, and then the intended colour in the exact same spot on the "COLOR" layer above it. A common way to do this is to first create your design in the "COLOR" layer and then copy every element to the "WHITE" layer and change the fill colour to the `RDG_WHITE` colour. Note that you cannot have other colours at all in the "WHITE" layer, so you may need to worry about any lines or fills or gradients.
9. Something quite similar happens with the gloss finish, if you ordered this. You create a layer _on top of_ the "COLOR" layer called either "GLOSS-V" (for a shiny gloss) or "GLOSS-M" (for a matte one), copy the shapes you want to apply the gloss finish to into this layer, and change their colour to `RDG_GLOSS` from the Roland swatch. (The CMYK spot colour is `(50,25,25,0)`.)

Now let's talk about Affinity Designer. It's an app that works on most platforms, including iPadOS, and can be bought for a reasonable one-off fee. I don't know if it's as good as Illustrator, but it worked well for me and was reasonably intuitive. In practice, the approach you might take to complete a design using Affinity Designer looks a bit like this:

Import the Roland "spot colour" swatches for white and gloss. There are a few floating around, but I used the ["PachyVersa" palette](https://www.pachydermpedals.com/assets/resources/PachyVersa.afpalette) from the [Pachyderm tutorial](https://www.pachydermpedals.com/tutorials/2020-12-27-angry-charles-tutorial/#rolad-swatches) and imported it as an _Application palette_ in Affinity. More on that process [here](https://forum.pedalpcb.com/threads/tayda-uv-printing-roland-swatches-for-affinity.5699/). With this installed, you can pick the relevant swatch in the Affinity colour picker to get the right colour.

Start with a template that sets up the right artboart dimensions (e.g. 62x117mm for a 125B enclosure) and layers. I used the "Tayda 3 Knob" one from [this page by Pachyderm pedals](https://www.pachydermpedals.com/tutorials/templates/), downloading the Affinity Designer file. Make sure it's set up with the CMYK colour space.

The Pachyderm template sets up a "background" layer at the very bottom that's just a square in the colour of the enclosure. This won't be included in the final export, but it's very useful to get a sense of how the design actually looks. You can use the Pantone swatch in Affinity designer to pick the correct Pantone colour for your enclosure if you ordered it painted from Tayda. On top of this, there are other layers that cover the position of drill holes, outlines to show the sizes of knobs and switches, and more stylised images that show how knobs and switches might actually look. Again, these layers are not used by Tayda and must be removed from the final PDF export, but they are important aids to make sure the layout will work in practice. And in-between we have the "WHITE", "COLOR", and "GLOSS" layers (which should be renamed "GLOSS-V" or "GLOSS-M" depending on whether you will select the varnish or matte finishes) where the design itself will go.

The next step is to make sure the markers for drill holes, knobs, and switches are in the exact same place as they are on your drill template. In Affinty Designer, the _Transform_ panel lets you enter a specific position and size for a selected object, in mm. When you do this, you first want to lock aspect ratio under _Dimensions_ so height and width are changed in proportion, and choose the _centre_ _Anchor_ point, so that when you update the position X,Y coordinate, you are moving the centre of the shape.

Getting the size right is pretty straightforward. For example, if you are planning to use 22mm knobs, you set the dimensions on the knob graphic to 22mm. If you want to draw the exact holes that will be drilled (which may or may not be needed, given knobs and switch nuts will be larger than the hole anyway), you can use the diameter specified on the drill template. However, getting the X,Y position correct requires a little bit of maths. This is because the Tayda drill template coordinate system treats `(0, 0)` as the _centre_, but Affinity will treat `(0, 0)` as _top left_ on the enclosure. The translation can be done like so, assuming a 125B 62x117mm enclosure:

```
Tayda X = -18.5mm
Tayda Y = 38.1mm

Enclosure width = 62mm
Enclosure height = 117mm

Affinity X = (Enclosure width / 2) + Tayda X => 12.5mm
Affinity Y = (Enclosure height / 2) - Tayda Y => 20.4mm
```

Here, the Tayda point of `(-18.5, 38.1)` will be towards the top left of the panel. The equivalent Affinity coordinate would be `(12.5, 20.4)`.

Next, create the required design on the "COLOR" layer. Simple is usually better.

Everything has to be a vector. If you want to import a file that's shared as JPEG, GIF, PNG or similar bitmap image, you will need to vectorise them first. I had the best result using [this online service](https://vectorizer.com), importing an SVG file, and then copying the relevant curves from the SVG "out" so they lived directly on the "COLOR" layer, before making further edits. You can right-click (two-finger tap) on a shape in Affinity and choose _Convert to Curves_ to turn sub-layers into top-level shapes, which I have read makes it more likely Tayda will be able to print the design. You need to do the same for all text boxes prior to export, so that the text is represented as vector lines rather than embedded text. Without this, you may not get the right font on the printed design.

Nothing should overlap. If you have a shape on top of another shape, you need to create a "cutout" in the underlying shape. The [Tayda UV printing instructions](https://www.taydaelectronics.com/hardware/enclosures/enclosure-uv-printing-service.html) talk about this (look for cats and houses), but the way I most effectively managed to do this in Affinity was a little dance of: Select the top shape. Copy to clipboard. Select both top and bottom shapes. Use the Affinity "object joining" toolbar (at the top when using the standard selector tool) to _subtract_ the shapes. This should leave a gap in the bottom shape. Immediately paste the copied object back so it slots into place. A bit fiddly, but works fine.

If you want white coloured text or lines, you need to do this on the white layer only using the special `RDG_WHITE` spot colour, and leave a gap on the "COLOR" layer.

<white>

<gloss>

<export>
