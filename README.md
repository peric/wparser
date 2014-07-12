# wparser

## Purpose

I need this parser to get the data which I'll need for my final exam. While writing it, I've decided to open source it so that maybe someone else can also find it useful or even contribute.
I doubt someone will find all those attributes useful but at least maybe you can get an idea of how to pull some specific data from websites.
I still didn't implement all the attributes that I've wanted, because for some of them I still didn't manage to find a solution.
Feel free to use this parser, contribute to it (by fixing or adding stuff), give me suggestions for better implementation or whatever else you want.

## List of attributes

* 'url'
    - type: string
    - Website url
* 'text'
    - type: number
    - Overall amount of text
* 'html_elements'
    - type: number
    - Number of all HTML elements used on a website
* 'headings'
    - type: number
    - Number of headings (<h1>, <h2> etc)
* 'paragraphs'
    - type: number
    - Number of <p> HTML tags used on website
* 'images'
    - type: number
    - Number of images included with <img> tag
* 'font_families'
    - type: number
    - Number of all font families used on a website
* 'font_sizes'
    - type: number
    - Number of font sizes (assigned with pixels, % and em - as one of the most used) used on a website
* 'links'
    - type: number
    - Number of links used on a website
* 'divs'
    - type: number
    - Number of div HTML tags used on a website
* 'ids'
    - type: number
    - Number of id attributes in HTML code
* 'classes'
    - type: number
    - Number of class attributes in HTML code
* 'css_external'
    - type: number
    - Number of external CSS sources (seperate CSS files)
* 'css_internal'
    - type: number
    - Number of internal CSS sources (under <style> tags)
* 'css_inline'
    - type: number
    - Number of inline CSS definitions (under style attribute)
* 'css_declaration_blocks'
    - type: number
    - Number of CSS declaration blocks
* 'css_prefixes'
    - type: boolean
    - Whether website is using experimental CSS (browser prefixes etc)
* 'js_sources'
    - type: number
    - Number of all JavaScript sources
* 'meta_tags'
    - type: number
    - Number of meta tags in the <head> of HTML file
* 'has_meta_keywords'
    - type: boolean
    - Check if website has any meta keywords 
* 'has_meta_description'
    - type: boolean
    - Check if website has any meta description
* 'rss'
    - type: boolean
    - Check whether website is using RSS or not
* 'import'
    - type: boolean
    - Check if there is “@import” rule used in CSS source code
* 'twitter_bootstrap'
    - type: boolean
    - Check whether Twitter Bootstrap is used
* 'html5'
    - type: boolean
    - Check whether HTML5 tags are used
* 'html5_tags'
    - type: number
    - Number of used HTML5 tags
* 'css_transitions'
    - type: boolean
    - Check whether CSS transitions are used
* 'flash'
    - type: boolean
    - Detect whether Flash is used
* 'page_weight'
    - type: number
    - Web page weight in kb
* 'media_queries'
    - type: boolean
    - Check whether media queries are used
* 'conditional_comments'
    - type: boolean
    - Check whether conditional comments in CSS are used
* 'included_multimedia'
    - type: boolean
    - Check if there is included multimedia (video, audio etc.)
* 'minified_css'
    - type: boolean
    - Detect whether any of CSS files are minified
* 'font_families_list'
    - type: string
    - List of all used font families
* 'h1_font'
    - type: string
    - Font used for <h1> element
* 'h2_font'
    - type: string
    - Font used for <h2> element
* 'h3_font'
    - type: string
    - Font used for <h3> element
* 'h4_font'
    - type: string
    - Font used for <h4> element
* 'h5_font'
    - type: string
    - Font used for <h5> element
* 'p_font'
    - type: string
    - Font used for <p> element
* 'a_font'
    - type: string
    - Font used for <a> element
* 'reset_css'
    - type: boolean
    - Check whether reset.css is used
* 'normalize_css'
    - type: boolean
    - Check whether normalize.css is used
* 'css_pseudo_elements'
    - type: boolean
    - Check whether CSS pseudo-elements are used 
* 'no_js'
    - type: boolean
    - Check whether no-js is used for older browsers

## Still not implemented list of attributes

* 'preprocessors'
    - type: boolean
    - Detect whether website is using preprocessors (like Sass, Less etc.)
* 'frameworks'
    - type: boolean
    - Detect whether website is using some kind of frontend frameworks (backbone.js, ember.js, angular js. etc.)
* 'cms_used'
    - type: boolean
    - Detect whether website is using some kind of CMS
* 'color_palette'
    - type: string
    - Detect website color palette - based on website screenshot. Should be somehow possible with https://github.com/lokesh/color-thief
* 'dominant_color'
    - type: string
    - Dominant color used on a website
* 'colors'
    - type: number
    - Number of different colors used in CSS
* 'css_errors'
    - type: number
    - Number of errors in CSS files. Should be somehow possible to get this information through w3c validator API
* 'html_errors'
    - type: number
    - Number of HTML errors. Should be somehow possible to get this information through w3c validator API
* 'sprite_images'
    - type: boolean
    - Detect whether sprite images are used

## Requirements

### Set up phantomjs

http://phantomjs.org/download.html

## Run

```
phantomjs wparser.js test/test.csv
```

## Input

As an input to a parser, as an parameter you give CSV file. You can find an example in [test/test.csv](test/test.csv). Be sure to keep the same structure.

## Output

Output is CSV file named output.csv, which you'll find in 'output' directory.

## TODO

* problem with cross browser requests -> how to properly get some css files? Maybe I can write an service in python or some other language which can handle this?
* implement color-thief - so that we can extract color pallete, most used colors etc - this data will be extracted from the screenshots
* use confess.js to get a list of requests etc - https://github.com/jamesgpearce/confess