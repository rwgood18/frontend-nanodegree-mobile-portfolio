Here is a link to my version of Cameron's portfolio http://rwgood18.github.io/frontend-nanodegree-mobile-portfolio/

I had no trouble optomizing index.html for speed. However, I struggled with pizza.html.  I made a lot of improvements, but it is not running at 60 fps.  I spent a long time working on it. It seems like the only way to improve the function resizePizzas() is to render all of the pizzas at once. As far as I know, there is no way to select multiple elements without creating a node list and iterating through it. I therefore do not know how to go about optimizing resizePizzas(). As for updatePositions(), I was able to reduce a lot of lag by removing costly functions from loops. The page is much better, but the fps meter does not reflect it.

To optomize index.html, I eliminated all render blocking CSS and JavaScript by inlining it. Then I minified index.html and set unnecessary stylesheets and scripts to be loaded asyncronously. 

To optomize pizza.html, I minified main.js and removed content from loops that did not need to be there.  For example, I cached a copy of Math.sin function outputs in an array so that the for loop inside updatePositions() did not have to call "Math.sin((num / 1250) + (i % 5))" every time through the loop.  I also added a viewport specification to increase compatibility with mobile devices. I experimented with requestAnimationFrame(), but it did not seem to be the right tool.


Index.html:
Initial Mobile Pagespeed Score: 28
Current Mobile Pagespeed Score: 92

Pizza.html:
Frames per Second is not much better according to the meter in Chrome Developer Tools. However, the user experience score on Google's PageSpeed Insights is vastly improved.