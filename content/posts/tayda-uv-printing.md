+++
title = 'Tayda enclosure UV printing for guitar pedals'
date = 2024-03-07T21:00:00Z
draft = true
+++

[Tayda Electronics](https://www.taydaelectronics.com) is an online electronics store in Thailand, which is popular with guitar pedal builders for supplying both components and hardware for DIY and hobby projects. I have built many pedal from [Jeds Peds](https://www.jedspeds.co.uk), who sell a bewildering array of PCB pedal kits and has a great community on Facebook.

The kits arrive by default with unpainted enclosures, which you can decorate yourself, and that's part of the fun. Most people use spray painting and home-printed waterslide decals for this, but after my first batch of pedals, I decided that painting is my least favourite part of the process. It requires a level of patience and consistency that I don't possess, is sensitive to temperature and humidiy, and makes a mess. And more importantly, even with base coats, multiple colour coats, and clear top coats, my pedals all chip and ding too quickly.

There are better ways. Commercial enclosures will commonly be power-coated, which is more durable, and will have any designs printed on them directly, rather than applied via a decal. And Tayda has a service that lets you do both. It's not _entirely_ obvious how it works, though, so here is my attempt at documenting the process. I learned all of this form others, in particular [this tutorial](https://www.pachydermpedals.com/tutorials/2020-12-27-angry-charles-tutorial/), [this forum thread](https://forum.pedalpcb.com/threads/steggo-studios-tayda-uv-printing-tutorial-part-1.15268/), and [this video series](https://youtu.be/iH_k_C3WFLU?si=40jGqZ2HyuiLko-G), as well as advice and examples from David Summers of the Jeds Peds forum.

The basic idea is as follows:

- Get the PCB and components you need. Tayda does sell some PCBs and a good range of components, though in my case I would get both from Jeds. (You want to order the PCB, components, and off-board components like jacks and switches, but not the "full kit" option that includes the enclosure itself.)

- Order the enclosure from Tayda, in the colour you want. It obviously needs to be big enough for the pedal you're making. Enclosure sizes have funny names like 125B (a common size used by Jeds Peds in their kits), 1590BB, etc. For example [here is the product page](https://www.taydaelectronics.com/hardware/enclosures/1590b-style-1.html) for 125B style enclosures. Note down the Pantone colour name - it'll come in handy later.

- Order the [Enclosure Custom Drill service](https://www.taydaelectronics.com/hardware/enclosures/enclosure-custom-drill-service.html) from Tayda for the relevant enclosure type. For example, [this is the 125B drilling service](https://www.taydaelectronics.com/hardware/enclosures/enclosure-custom-drill-service/125b-custom-drill-enclosure-service.html), which will let you ask Tayda to drill the face (for knobs and switches), top and/or sides (for jack and power sockets) for you. You will create a _custom drill template_ that will let you specify precisely where the holes go and how large they are.

- Order the [Enclosure UV Printing service](https://www.taydaelectronics.com/hardware/enclosures/enclosure-uv-printing-service.html) from Tayda. This page has a lot of detail of how the service works, and you must read it all the way through, though I'll also describe some of the pertinent points below. You basically order the relevant size of UV printing (like [this one for printing on the face of a 125B enclosure](https://www.taydaelectronics.com/hardware/enclosures/enclosure-uv-printing-service/125b-uv-printing-service.html)), and probably also the optional [gloss layer printing service](https://www.taydaelectronics.com/hardware/enclosures/enclosure-uv-printing-service/custom-uv-gloss-layer-service.html).

- Create an account on the [Tayda Drill service](https://drill.taydakits.com/dashboard). This is a separate app by the same company. You _must_ use the same email address for the drill service account and the Tayda web store account, or you won't be able to link your order to the drill template.

- In the drill tool, there is a web interface for defining a drill template. You can find [existing ones that others have shared](https://forum.pedalpcb.com/forums/drilltemplates/) as a starting point, or define your own from scratch. Essentially, you place holes on a coordinate system (where 0,0 is the centre of the enclosure) and define how big each one should be (**Note:** You must add 0.2mm for the powder coat). A little whlie after you've placed your order on the main Tayda web shop, you'll be able to link the enclosure you've bought to a specific drill template.

- Create an appropriately formatted PDF that will be used for UV printing the design. The strong recommendation from Tayda is that you do this in Adobe Illustrator. The problem with that, is the Illustrator is expensive. [Affinity Designer](https://affinity.serif.com/en-gb/designer/) is a popular alternative. I used the iPad version for my design, which is available in the App Store. There are a lot of rules and nuances to getting the PDF right, and if it's wrong Tayda may at best send it back to you, and at worst print something that will look wrong. More on this below.

- Upload the UV printing PDF file in the Tayda drill tool and link it to your order.

- Wait patiently for a few weeks.
