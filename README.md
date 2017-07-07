## Design

**Versioning**

Most recent file:

/client/year/projectname/01_working/file_v3.jpg

Old files

/client/year/projectname/OLD/file_v1.jpg

/client/year/projectname/OLD/file_v2.jpg

Print specific projects

/client/year/Print/01_working/

/client/year/Print/03_proofs/

/client/year/Print/04_print_final/

**File management**

Each project is split into multiple design rounds:

> <sub>* Design exploration (Initial moodboards, art direction)

> <sub>* Design (Designs to be presented to the client)

> <sub>* Development (Design production and hand off)

Each major design update is saved as a new file with an updated version number.

## Photoshop documents

**Content**

For the love of god, use REAL content wherever possible. Our clients have content we can use, so do so. Using real content will help you understand:

> <sub>* interface gaps

> <sub>* truncation issues

> <sub>* problematic large chunks

> <sub>* missing content

> <sub>* extraneous content

> <sub>* and a whole lot more

You have no excuse now. Go forth and use REAL CONTENT!

**Setup for Retina Mockups**

Mockups should be created at 2× resolution by default. This can make thinking in consistent units hard (2px in PSD == 1px in CSS). The recommended way to ease this pain is to set up Photoshop documents to use pt units in such a way that 1pt in Photoshop equals 1px in CSS:

When creating a new document, set the Resolution to 144px/inch. If updating an existing document, do this in Image > Image Size (make sure Resample is disabled).

Open Photoshop > Preferences > Units and Rulers.

In the Units fieldset, change both Rulers and Type to Points.

In the New Document Preset Resolutions fieldset, change the Screen Resolution to 144px/inch.

In Photoshop > Preferences > Guides, Grid and Slices, Make sure to leave the Gridline and Subdivision settings in pixel units, not points. Using point for snapping is buggy and will lead to errors. Example: if you want gridlines every 8 points, set this value to 16 pixels.

Note: some palettes and inputs (such as Transform) do not respect the unit preferences. However, they do remember the last unit used so as you work in points they will come to reflect the new preferred unit.

**Resources for Creating Mocks**

PSD TEMPLATES ON /omshare/Internal Templates and Stuff/web/

**Modules & Linked Smart Objects**

Photoshop CC now supports linked smart objects. Following in the footsteps of InDesign and Illustrator, users can now drop linked files into Photoshop documents. When a linked smart object has been placed in a PSD, Photoshop will detect changes to this linked file and you can update them as needed across all PSD's. This allows us to modularize our elements in a similar fashion to the way our CSS has been modularized.

Please break up your PSD's into logical modules and place these modules as linked smart objects in your PSD's. Here's how to place a linked smart object:

File > Place Linked

I've put together this diagram to help:

![](null)

As far as naming conventions go, for the modular PSD's we'll be following in the same footsteps as the CSS Style Guide and its reference to Component Oriented Naming, and for the non-modular PSD's we'll follow our standard file naming and folder conventions . So click the links and study up.

*This system can get unruly and complicated pretty easily, but its a HUGE help on massive projects with lots of comps. If you're working on a quick small project, you don't HAVE to use this structure, its probably overkill.*

You'll also notice the above diagram has a styleguide.psd. This segues nicely into our next topic:

**Styleguide.psd**

Every project should have its own styleguide.psd file that contains all the elements of a projects interface. This style guide can they be used by developers to create the necessary CSS markup for interface elements, without having to hunt through an entire project's worth of mocks.

As identified by the diagram above, the style guide should actually consist of components that are linked smart objects. This allows us to maintain that the compontent.psd file is the master copy and that updates to it propagate through all their linked PSDs.

Find the template on omshare/templates/*UI Style Guide Template > style-guide-template.psd*

**Paragraph & Character Styles**

A - Margins

Rather than dealing with new type layers, and soft carriage returns, try to setup your typography system using the paragraph and character panels. The Paragraph spacing options allow you to add space before and after paragraphs, super handy for blocks of text!

B - Letter Spacing

Try not to use it, but if you must use increments of 50. Increments of 50 generally translates to 1px + or - but this scales with the font size, so use your judgement.

C - Hyphenation

Since CSS doesn't support hyphenation, make sure hyphenation is turned off in Photoshop as well. Check the Paragraph panel.

![](null)

**Vector Shapes**

Use vector shapes whenever possible. Photoshop CC now supports native non-destructive transform on all vector shapes. So if you make sure you're building rounded rectangles with the rounded rectangle tool you can now adjust those rounded corners in the path panel, even after transforming the rectangle. Finally, Illustrator like vector tools, HOORAH!

**Image Embedding**

We all love embedding our clients sweet photos into image carousels (they send over the best photography!) When you do, make sure the image is embedded at 100% height and 100% width and turn that image into a smart object. Now when you resize to fit, you'll be doing so non-destructively. Smart Objects FTW.

Also good idea to save these into assets ready for the web - scaled, cropped, optimized etc. 

**Colour Profiles**

Make sure you disable colour management in Photoshop. We want our mocks to be easy for developers, and since there are no colour management options in development, we gotta scrap 'em in Photoshop too. To do this:

Edit > Color Settings

![](null)

**Colour Swatches**

When working on a client project, make sure to check the assets folder for a colour swatches panel. Every project should have one, and if it doesn't please create one. Couple things to note here:

> <sub>* name colours using our scss naming syntax

> <sub>* use the swatches present manager to easily manage colour swatches

> <sub>* large list view is great for a list of colours and their titles

![](null)

**Sharp Edges**

Make sure your snap to pixels and grid tools are enabled. We want those pixels to be as sharp as possible, nobody likes soft blurry edges.

**Plugins**

We use a few plugins to increase efficiency and improve our workflows. They are:

> <sub>* [GuideGuide](http://guideguide.me/) - pixel accurate columns, rows, midpoints, and baselines can be created based on your document or selection with the click of a button

> <sub>* [Composer](https://jasonforal.com/composer/) - Update multiple layer comps in Photoshop with just one click

**Layer organization and naming**

Group and label (ideally relatable to the development) your PSD Layers.

Try to keep objects organised by grouping them into multiple layers and sublayers. A decent file organisation helps you not only to establish a proper system for your design, but also to hand-off your files easier and to find your way through archived files much faster.

Keep the folder structure as flat as possible by not creating too many sublayers. This makes it easier to get an immediate overview over your system.

Group elements which appear on every page of your website (header or footer elements) into one single layer either at the top or at the bottom of the panel, rather than duplicating them into every single layer.

Use one document for the whole system if possible (one document = one system). It will make it easier to copy elements from one page to another and share the same libraries (e.g. Swatches and Styles).

Stick to the same file naming and order for your exported files. This makes it easy when exporting layer by layer for a presentation and sharing your files. (See • General file handling for consistent layer naming).

![](null)

## 3. Grid

Grid-based design is a foundational aspect of Overhaul's design philosophy. Every system we design is based on a grid.

View > New Guide Layout

![](null)

Working with a grid is an essential starting point for any project. It is the controlling principle helping to create an organized graphic system that is tight and easy to understand, while also providing a framework for making design choices.

The grid defines a mathematical system for the design and provides rules for the size and placement of objects within it. The number of possibilities for any given decision is reduced, making it faster to explore and iterate solutions.

For interactive projects we use the Bootstrap 12 column Grid. This makes moving to development easy and no guesswork required.  Makes naming classes for the columns simple and consistent between projects. 

> <sub>* Download an example/starter [PSD Browser Template](http://#) with predefined break points, columns/grid layers. 

> <sub>* Compare devices regarding sizing and resolution on [Google Device Metrics.](https://material.io/devices/)

![](null)

Example grids for desktop to mobile

## 4. Styles / Style Guides

We do style guides for the majority of our website projects. When a project has a CMS we are always going to need a set of elements (h1, h2, form inputs, buttons, list styles etc).

LINK TO TITAN This reduces the possibility of us missing something a user might make with their CMS tools, also make the site easier to maintain in the future. 

> <sub>* Mock up everything including skeleton load elements

> <sub>* Download an example/starter Styles PSD

> <sub>* Reference http://www.maban.co.uk/projects/front-end-style-guides/

## 5. Atomic / Modular design 

Mainly when a project is CMS driven we use a modular design approach. Read more below until I can write more here. 

> <sub>* Reference  http://bradfrost.com/blog/post/atomic-web-design/

**Responsive** 

[Google Design — Device Metrics](https://design.google.com/devices/)

[Google Design — Responsive UI](https://material.google.com/layout/responsive-ui.html#)

[Google Design — Resizer](http://design.google.com/resizer/)

