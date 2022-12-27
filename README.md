# luxe
An exploration of a surveillance tech-fueled present. The name, concept and references in the piece are largely inspired by the work of Chris Gilliard and David Golumbia on what they call "[luxury surveillance](https://reallifemag.com/luxury-surveillance/)."

I made the 3d models in Blender over winter break 2021. Winter break of this year (2022) I finally got around to transforming them into a web app. (A lot has changed in a year, but a lot has stayed the same. Last year, I named this project "subtle dystopia"; it was intended to be "an exploration of a surveillance tech-fueled future." But as Gilliard [writes](https://www.theatlantic.com/technology/archive/2022/10/amazon-tracking-devices-surveillance-state/671772/) about surveillance tech in *The Atlantic*, "It would be a bit glib—and more than a little clichéd—to call this some kind of technological dystopia. Actually, *dystopia* wouldn't be right, exactly; Dystopian fiction is generally speculative, whereas all of these items and services are real.") I made the images in the piece in Sketch and used three.js for the web stuff.

- Use the arrow keys, dragging and pinching/scrolling (zooming) to look around. (Screenshot of the room below~)
- Photosensitivity warning — the CSS objects sometimes flash when rendering.
- Alt text for the room: Two adjacent grey walls and grey floor forming a corner. Along the wall on the left are a lamp in the shape of a small potted tree plant; a glass table with a speaker, tablet (showing a "doorbell cam"), monitor (showing a "WARNING: CHEATING; Keep your face in view of your webcam." message) and a chair; and a blue light in the shape of a cloud. Along the wall on the right are a lofted bed with a blue blanket and red and green pillows, underneath which are two drawers; a shelf with an icosahedron-shaped lamp, a Rubik's cube, two books and slippers; a TV cycling through three fake ads ("no more bad dates," "NEVER COOK AGAIN" and "SELL YOUR DATA YOUR WAY"); and a mirror with glowing text that reads "body scan mode." In the middle of the room are a blob-shaped rug atop which stands a robotic orange cat. Above the two walls are links to this repo and its README.

(On my computer it works best on Chrome. On Safari it reloads continuously due to energy overuse, but this might be because my computer's old, but there's also a bug with the CSS object displays; going to look into these more in the future. If you try on Safari, be sure to go to Menu > Develop > Experimental Features and check WebGL 2.0.)

TODOs / bugs:
- Make it less energy-intensive
- Safari CSS object offset
- Sound randomly stops playing / doesn't work

Inspiration for various parts of the piece:
- [A Detroit community college professor is fighting Silicon Valley’s surveillance machine. People are listening.](https://www.washingtonpost.com/technology/2021/09/16/chris-gilliard-sees-digital-redlining-in-surveillance-tech/) — Will Oremus for *The Washington Post*
- [Surveillance shift: San Francisco pilots program allowing police to live monitor private security cameras](https://www.theguardian.com/us-news/2022/oct/04/san-francisco-police-video-surveillance) — Johana Bhuiyan for *The Guardian*
- [Cheating-detection companies made millions during the pandemic. Now students are fighting back.](https://www.washingtonpost.com/technology/2020/11/12/test-monitoring-student-revolt/) — Drew Harwell for *The Washington Post*
- The mirror is inspired by the Amazon Halo body fat scanner.
- The speaker is playing lofi music made in the [Google Magenta Lo-Fi Player](https://magenta.tensorflow.org/lofi-player), which incorporates machine learning (e.g. to generate new melodies). It's inspired by a tweet I saw a long time ago and can no longer find, which I think was roughly about how lofi and a few other tech-y cultural artifacts exemplify the way Silicon Valley colonizes culture and makes things boring. I'm explaining this terribly, but one of the replies cited Kyle Chayka's *Verge* essay [Welcome to Airspace](https://www.theverge.com/2016/8/3/12325104/airbnb-aesthetic-global-minimalism-startup-gentrification), which tackles this topic (roughly, I don't remember the tweet that well) and explains it much better than me.

Credits:
- [The YouTube tutorial series that helped me learn how to use Blender](https://www.youtube.com/watch?v=nIoXOplUvAw)
- Room design inspired by [Bruno Simon's "My Room in 3D"](https://github.com/brunosimon/my-room-in-3d)
- Initial three.js experimentation: [GabrielRamirez's threejs-gltf-template](https://github.com/GabrielRamirez/threejs-gltf-template)
- Later experimentation and project setup: [mrdoob's three.js webgl_loader_draco example](https://github.com/mrdoob/three.js/blob/master/examples/webgl_loader_draco.html)
- [CSS3DRenderer.js](https://github.com/mrdoob/three.js/blob/master/examples/jsm/renderers/CSS3DRenderer.js), [DRACOLoader.js](https://github.com/mrdoob/three.js/blob/master/examples/jsm/loaders/DRACOLoader.js), [GLTFLoader.js](https://github.com/mrdoob/three.js/blob/master/examples/jsm/loaders/GLTFLoader.js), [OrbitControls.js](https://github.com/mrdoob/three.js/blob/master/examples/jsm/controls/OrbitControls.js) and [three.module.js](https://github.com/mrdoob/three.js/blob/dev/build/three.module.js) from three.js
- [Google Magenta Lo-Fi Player](https://magenta.github.io/lofi-player/)
- [Flickering neon lights in CSS (for the monitor and mirror screen contents)](https://codepen.io/GeorgePark/pen/MrjbEr)
- Incorporating CSS objects: followed [this](https://github.com/mrdoob/three.js/blob/master/examples/css3d_periodictable.html) example
- Cat meow sound effect from <a href="https://pixabay.com/sound-effects/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=music&amp;utm_content=5928">Pixabay</a>

Random notes on process:
- Created model in Blender with colors, textures, lights, etc.; fiddled with it until it looked nice when rendered
- Baked textures in groups, by material, following [this](https://www.youtube.com/watch?v=eYvgFWEiNp8) tutorial
    - 4096x4096, reduce light bounces to speed it up, make sure Image Texture is selected in the shading editor and the dropdown is filled with the relevant image
- Connected baked textures to corresponding materials in shading editor, exported as .glb
- Switched to using cdn when deploying
- The CSS objects render on top of the other objects, which is kind of annoying. Experimented with adding image textures to the screens but it was kind of a hassle. Didn't plan ahead for this, but for future projects do this in Blender (e.g. a lot of the screens are static so there's no need to do them in three.js). (TODO: try to find workaround.)
- On Safari, go to Menu > Develop > Experimental Features and check WebGL 2.0. Although at a certain point it stopped working on Safari entirely (would constantly reload due to energy overuse.) Might be because my laptop is a bit older (?)
- On Safari, CSS objects don't display in the correct position. Possibly relevant: [this](https://github.com/mrdoob/three.js/issues/19854)
- Future work: [computer fan go brrr](https://discourse.threejs.org/t/fans-blowing-up-high-cpu-usage/15949/2)

![A dimly-lit room with various tech gadgets and red-green-blue color scheme](https://raw.githubusercontent.com/amphinomid/luxe/main/assets/screenshot.png)