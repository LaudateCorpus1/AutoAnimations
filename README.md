# AutoAnimations
_"It's like auto-tune for web pages"_

Automatically animate all inserted and removed DOM elements with good defaults:
- Slide down/up for elements with display=block & position=static
- Fade in/out for all others
- Elements with existing CSS transitions or animations will be left alone
- Uses velocity.js to assure smooth 60fps animations even in mobile


<img src="http://i.imgur.com/EMN0gPG.gif" height=200px/>

compare with http://todomvc.com/examples/react/ (that has no autoanimate)

##USAGE
Just include this script, and add an animation-duration to your css, e.g. 

<pre>* { 
    animation-duration: .2s; 
}</pre>

####NOTES
- Elements shown/hidden using the style's display (e.g. jquery's show, hide and toggle) will not be animated.
- In javascript UI frameworks (e.g. React) it's recommended that this script is run after first render 
- You can add this as the URL of a bookmark to create a bookmarklet to test it in any web page:
    - <pre>javascript:(function(){document.styleSheets[0].insertRule("* {animation-duration: .2s}", 0);document.body.appendChild(document.createElement('script')).src='https://rawgit.com/OutSystems/AutoAnimations/master/AutoAnimations.js';})();</pre>
- This overrides HTMLElement prototype methods, so it's a huge hack (only a POC) and there might be several side effects. 

####EXCEPTIONS
If you don't want some element to automatically animate (e.g. external libraries) just set its animation-duration to 0s, e.g. :
<pre>.SomeCustomComponent, .SomeCustomComponent * {animation-duration: 0s; }  </pre>
