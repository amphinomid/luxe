# luxe
An exploration of a surveillance tech-fueled present. The name, concept and references in the piece are largely inspired by the work of Chris Gilliard and David Golumbia on what they call [luxury surveillance](https://reallifemag.com/luxury-surveillance/).

I made the 3d models in Blender over winter break 2021. Winter break of this year (2022) I finally got around to transforming them into a web app. (A lot has changed in a year, but a lot has stayed the same. Last year, I named this project "subtle dystopia"; it was meant to be "an exploration of a surveillance tech-fueled future." But as Gilliard writes in [The Atlantic](https://www.theatlantic.com/technology/archive/2022/10/amazon-tracking-devices-surveillance-state/671772/), "It would be a bit glib—and more than a little clichéd—to call this some kind of technological dystopia. Actually, *dystopia* wouldn't be right, exactly; Dystopian fiction is generally speculative, whereas all of these items and services are real" — hence the concept shift.) I made the images in the piece in Sketch and used three.js for the web stuff.

(On my computer it works best on Chrome, but it might be because my computer's old. On Safari, be sure to go to Menu > Develop > Experimental Features and check WebGL 2.0.)

Inspiration for various parts of the piece:
- [A Detroit community college professor is fighting Silicon Valley’s surveillance machine. People are listening.](https://www.washingtonpost.com/technology/2021/09/16/chris-gilliard-sees-digital-redlining-in-surveillance-tech/) — Will Oremus for *The Washington Post*
- [Surveillance shift: San Francisco pilots program allowing police to live monitor private security cameras](https://www.theguardian.com/us-news/2022/oct/04/san-francisco-police-video-surveillance) — Johana Bhuiyan for *The Guardian*
- [Cheating-detection companies made millions during the pandemic. Now students are fighting back.](https://www.washingtonpost.com/technology/2020/11/12/test-monitoring-student-revolt/) — Drew Harwell for *The Washington Post*
- The mirror is inspired by the Amazon Halo.
- The speaker is playing lofi music made in the [Google Magenta Lo-Fi Player](https://magenta.tensorflow.org/lofi-player), which incorporates machine learning (e.g. to generate new melodies). It's inspired by a tweet I saw a long time ago and can no longer find, which I think was roughly about how lofi and a few other tech-y cultural artifacts represent how Silicon Valley colonizes culture and makes things boring. I'm explaining this terribly, but one of the replies cited Kyle Chayka's *Verge* essay [Welcome to Airspace](https://www.theverge.com/2016/8/3/12325104/airbnb-aesthetic-global-minimalism-startup-gentrification), which explains it much better.

Credits:
- [The YouTube tutorial series that helped me learn how to use Blender](https://www.youtube.com/watch?v=nIoXOplUvAw)
- Initial three.js experimentation: [GabrielRamirez's threejs-gltf-template](https://github.com/GabrielRamirez/threejs-gltf-template)
- Later experimentation and project setup: [mrdoob's three.js webgl_loader_draco example](https://github.com/mrdoob/three.js/blob/master/examples/webgl_loader_draco.html)
- [CSS3DRenderer.js](https://github.com/mrdoob/three.js/blob/master/examples/jsm/renderers/CSS3DRenderer.js), [DRACOLoader.js](TODO), [GLTFLoader.js](TODO), [OrbitControls.js](TODO) and [three.module.js](TODO) from three.js
- [Google Magenta Lo-Fi Player](TODO — the actual player)
- [Flickering neon lights in CSS (for the monitor and mirror screen contents)](https://codepen.io/GeorgePark/pen/MrjbEr)
- Incorporating CSS objects: followed [this](https://github.com/mrdoob/three.js/blob/master/examples/css3d_periodictable.html) example
- Cat meow sound effect from <a href="https://pixabay.com/sound-effects/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=music&amp;utm_content=5928">Pixabay</a>

Random notes on process:
- Created model in Blender with colors, textures, lights, etc.; fiddled with it until it looked nice when rendered
- Baked textures in groups, by material, following [this](https://www.youtube.com/watch?v=eYvgFWEiNp8) tutorial
    - 4096x4096, reduce light bounces to speed it up, make sure Image Texture is selected in the shading editor and the dropdown is filled with the relevant image
- Connected baked textures to corresponding materials in shading editor, exported as .glb
- Made local copies of three.js code for stuff that required a constructor (the loaders and orbit controls)
- The CSS objects render on top of the other objects, which is kind of annoying. Experimented with adding image textures to the screens but it was kind of a hassle. Didn't plan ahead for this, but for future projects do this in Blender (e.g. a lot of the screens are static so there's no need to do them in three.js). (TODO: try to find workaround.)
- On Safari, go to Menu > Develop > Experimental Features and check WebGL 2.0. Although at a certain point it stopped working on Safari entirely (would constantly reload due to energy overuse.) Might be because my laptop is a bit older (?)