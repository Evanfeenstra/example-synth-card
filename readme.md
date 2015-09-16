<h3>Go to <a href="http://www.beatpush.com" target="_blank">BeatPush.com</a> to see this code in action. Click the "Synth" tab at the top of the page.</h3>

This is is not the entire code for the "synth-card" element, I removed pieces to make it easier to survey.

<h4>"Note" section</h4>
Here, you can drag and drop colors onto the outer circles, to sequence notes and play a melody. Check out the "handleTrack" function to see how that it done.

<h4>"FX" section</h4>
Paper-slider elements control different effect levels. The values of these sliders are bound to declared properties of the synth-card element, which makes it really easy to update them. If the filter slider needs to be changed from some non-UI source (a MongoDB document for instance), you can just call
```javascript
document.getElementById('synth-card').filter_setting=value;
```
The UI is updated because it is bound to this value, and the actual musical parameters are updated via the filter_settingChanged function on line 124.

<h4>"Mod" section</h4>
You can use the XY-pad to control two parameters of the synth sound. As you drag the dot around the screen, the synthesizer "wobble" is updated, as well as the CSS of the SVG element. This is accomplished with the attribute binding on line 48 style$="{{lfo_style}}"

Page selection animations are implemented without any javascript at all...Just bind the "selected" attribute of neon-animated-pages to the "selected" attribute of paper-tabs, and specify some animations eg. entry-animation="fade-in-animation" exit-animation="scale-down-animation"

