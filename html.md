# Meta tags in HTML
* meta tag provide metadata about the html document,
* typically we could use it to specify the page description, or keyword, or author.
* it set the viewport, tell the brower how to scale the screen for mobile device.
* it have some advantange for SEO,
* it specify the charset

# SEO
* search engine optimize, use for increase the rank of website. 
* the metadata is use for it.

# What is Character Encoding
* in order to display the page, a web brower must know which character set to use.
* the first charactor set is ascii.
* for now we use UTF-8, it almost cover all the character and symbol in the world.
* it specified in meta tag.

# Semantic html 
* semantic element is element with a meaning.
* it clearly describe its meaning to brower and developer.
* such as form, table, header, footer
* non-semantic element: div, span.

# What’s new in HTML5
* some new tag and new api
* such as the local storage api
* such as multimedia tag like vedio, audio.

# Canvas vs SVG
* canvas
    - canvas is a container for graphics, 
    - we use javascript to draw the graphic.
    - canvas is rendered pixel by pixel, after drawn, it forgotten by browser.
* SVG 
    - svg element is a container for svg graphic
    - is a language for describing 2D graphics in XML
    - in svg, each shape is remembered as an object.

# What does a DOCTYPE do
* it is an instruction to the web browser about what version of html it is.

# Can a web page contain multiple <header> /<footer> elements?
* you can, header and footer is semantic element, it is only a container.
* however, we should avoid to use multiple header in one page, because its meaningless.

# What is DOM
* document obejct model, it is a programming interface for html document.
* it represent the document as nodes and objects, so we can change its structure, style, and content.

# XHTML vs HTML5
+ HTML5
    - it include some new tags and new api.
    - such as some new semantic elements like header, footer, section
    - such as the multimedia element like audio and vedio.
    - some API such as the local storage, application cache.
+ XHTML
    - extensible html,
    - more strict than html
+ XML
    - extensible markup language
    - desing for store and transport data.

# Where should we put <link> and <script> and why 
* we should put link in head tag, because when we encounter the link tag, the html parser will be fetch data from server, and then use css parser to parse the css file.
if we put link in body, the time cost will be expensive, and the html also will re-rendered.
* script should be put at the bottom of the body. because the script may need to use the node from dom, if we put it in head tag, it will be an error.

# 508 policy / accessibility / aria

# script, defer and async tag.
+ async
    - the script will be fetched in parallel with html parsing, and execute as soon as it available.
    - use when the script is independent of any other script on the page.
+ defer
    - the script will be fetched in parallel with html parsing, and execute after the page parsing.
    - if the script relied on a fully-parsed dom.
+ without async and defer
    - the html parsing will be blocked, the script will fetched and executed immediately.

# What is iframe and how it works
* an iframe is display an web page within another web page, that means you embed another document into the current html element
* however, we could set the x-frame-option property in httpResponse to deny or sameorigin 
* deny means no one can load it in iframe
* sameorigin means only the page have same domain can load it.L

# responsive design
* responsive design is only about html and css, 
* we use media queries to change html structure for different screen size.
* to make our website looks good for all device

# what is target attribute of a.
* target is to specify where to open the link.
* such as _blank, will open a new tab

# windows.location
* windows location use to get the current url, and redirect to a new url.

# windows.navigator
* is an object contain the visitor browser's information
* such as browser version, language.