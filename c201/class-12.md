# Reading 12 Chart.js, Canvas

## The < canvas > element

***The Canvas API provides a means for drawing graphics via JavaScript and the HTML `<canvas>` element. Among other things, it can be used for animation, game graphics, data visualization, photo manipulation, and real-time video processing. The Canvas API largely focuses on 2D graphics.***

*the `<canvas>` element has only two attributes, width and height.*

*There are three functions that draw rectangles on the canvas:*
- `fillRect(x, y, width, height)` Draws a filled rectangle
- `strokeRect(x, y, width, height)` Draws a rectangular outline.
- `clearRect(x, y, width, height)` Clears the specified rectangular area, making it fully transparent.

*The canvas rendering context provides two methods to render text:*
- `fillText(text, x, y [, maxWidth])` Fills a given text at the given (x,y) position. Optionally with a maximum width to draw.
- `strokeText(text, x, y [, maxWidth])` Strokes a given text at the given (x,y) position. Optionally with a maximum width to draw.


***by [developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_usage)***

## Chart.js

***Chart.js is a JavaScript plugin that uses HTML5’s canvas element to draw the graph onto the page. It’s a well documented plugin that makes using all kinds of bar charts, line charts, pie charts and more***

*To draw a line chart, the first thing we need to do is create a canvas element in our HTML in which Chart.js can draw our chart.*

```
<canvas id="buyers" width="600" height="400"></canvas>
<script>
    var buyerData = {
	labels : ["January","February","March","April","May","June"],
	datasets : [
		{
			fillColor : "rgba(172,194,132,0.4)",
			strokeColor : "#ACC26D",
			pointColor : "#fff",
			pointStrokeColor : "#9DB86D",
			data : [203,156,99,251,305,247]
		}
	]
    }
    var buyers = document.getElementById('buyers').getContext('2d');
    new Chart(buyers).Line(buyerData);
</script>
```
***by [webdesignerdepot](https://www.webdesignerdepot.com/2013/11/easily-create-stunning-animated-charts-with-chart-js/)***