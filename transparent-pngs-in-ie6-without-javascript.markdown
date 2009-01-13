Type: Blog Post (Markdown)
Blog: Post-Swiftalism
Link: http://bryanjswift.com/reflections/transparent-pngs-in-ie6-without-javascript
Post: 216
Title: Transparent PNGs in IE6 Without JavaScript
Slug: transparent-pngs-in-ie6-without-javascript
Keywords: css
Status: publish
Date: 2008-09-18 03:36:37 -0500
Pings: On
Comments: On
Category: reflections

Most people developing complex designs for the web are making use of transparent 32-bit PNG images which are fantastic and beautiful and crisp in every modern browser. Sadly not all browsers in wide use are modern, namely Internet Explorer 6. In order to make transparency work in IE6 there are a number of JavaScript solutions available which generally work wonderfully well. However I recently had need to support a page in IE6 whose designs required transparent PNGs but for circumstances beyond my control did not permit me to use JavaScript at all.

After some consideration I had a realization, I didn't need my CSS to validate either. Since I was able to use invalid CSS I could make use of some dirty hacks in order to achieve my goal. The trick was that none of the images could be inline, so they were all implemented as background images. For each element which had a background image which was a transparent PNG I set the background image normally and then in the IE6 hack changed the background image to a blank.gif[^1] and then set the proprietary filter property the the element. The code ended up looking something like what is shown below and it worked like a charm under these admittedly narrow circumstances.

<pre lang="css">
#selectorId {
	background: url(/path/to/image.png) top left no-repeat;
	_background-image: url(/path/to/blank.gif);
	_filter: progid:DXImageTransform.Microsoft.AlphaImageLoader(src="/path/to/image.png", sizingMethod="scale");
}
</pre>

_**Update:** I have since learned the path to the image in the filter's source must be relative to the HTML document and not to the CSS file. Originally when I applied this technique this clarification eluded me because all of my image paths were absolute[^2]._

[^1]: a 1 pixel transparent image
[^2]: they started from the document root
