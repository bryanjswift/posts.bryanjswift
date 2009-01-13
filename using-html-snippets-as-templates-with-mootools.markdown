Type: Blog Post (Markdown)
Blog: Post-Swiftalism
Link: http://bryanjswift.com/thoughts/using-html-snippets-as-templates-with-mootools
Post: 207
Title: Using HTML Snippets as Templates with MooTools
Slug: using-html-snippets-as-templates-with-mootools
Keywords: javascript, mootools, web development
Status: publish
Date: 2008-09-04 20:35:48 -0500
Pings: On
Comments: On
Category: thoughts

I've been working a great deal with JavaScript Objects which are used purely to store data but which need to be performantly converted into HTML code blocks. In order to achieve this I created a function which searches for specific delimiters and replaces the delimiters with the Object's property of the same name.

The code to do this is fairly straightforward:

<pre lang="javascript">
/* This code is released under a MIT license */
String.implement({
	template: function(props) {
		var regex = /%(\w+)%/g;
		var newStr = this.replace(regex,function replacer(mid) {
			var key = mid.substring(1,mid.length-1);
			var value = props[key];
			if (typeof value === 'string') {
				return props[key];
			} else {
				return '';
			}
		});
		return newStr;
	}
});
</pre>

Using this function I can take a snippet of HTML and a JavaScript Object containing replacement information and easily turn the snippet into a useful String for user with the innerHTML property. For example, starting with the following HTML

<pre lang="html">
<div id="template">
	<div class="test">
		<p>%testName%</p>
		<p>%testDescription%</p>
	</div>
</div>
</pre>

I can execute this simple piece of JavaScript and get a useful HTML. The JavaScript and HTML output follow.

<pre lang="javascript">
var newHtml = $('template').get('html').template({
	'testName': 'This is just a test',
	'testDescription': 'Please do not be alarmed this is a simple test'
});
$('template').set('html',newHtml);
</pre>

The HTML will now look like the following

<pre lang="html">
<div id="template">
	<div class="test">
		<p>This is just a test</p>
		<p>Please do not be alarmed this is a simple test</p>
	</div>
</div>
</pre>

I've found this technique to be incredibly useful. Hopefully someone else will as well.
