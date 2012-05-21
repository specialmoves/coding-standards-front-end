#Coding standards front end

##Code formatting

##HTML

* Use Polygot Markup with the following emphasis:
	* Use XHTML compliant Boolean attributes e.g. <input type="text" required="required" />.
	* Use double quotation marks for attributes.
	* Use the minimized tag syntax, with a space before the closing slash, for void elements, e.g. <br />.
*Use consistent line breaks:
	*Add line breaks only between sibling sectioning elements & ARIA landmark roles.
	*Place inline tags on the same line.
	*Place block-level tags on a new line and indented.
	*Include templating serverside code as part of the nesting of elements.
	*Wrap long lines of text and treat as block-level elements, using 150 char length as a guide.

##CSS

###Example of style

	/* header */
		.action .action-information,
		.button .information:last-child {
			background: url("../images/generic-logo.png") no-repeat center 0 #fff;
			background-image:
				url("../images/generic-bg-bottom.png"),
				url("../images/generic-bg-top.png");
			border: 1px solid #000;
			-webkit-box-shadow: /* multiple properties on different lines */
				0 1px 3px rgba(0, 0, 0, .2),
				0 2px 6px rgba(0, 0, 0, .1);
			-moz-box-shadow:
				0 1px 3px rgba(0, 0, 0, .2),
				0 2px 6px rgba(0, 0, 0, .1);
			-ms-box-shadow:
				0 1px 3px rgba(0, 0, 0, .2),
				0 2px 6px rgba(0, 0, 0, .1);
			-o-box-shadow:
				0 1px 3px rgba(0, 0, 0, .2),
				0 2px 6px rgba(0, 0, 0, .1);
			box-shadow:
				0 1px 3px rgba(0, 0, 0, .2),
				0 2px 6px rgba(0, 0, 0, .1);
			color: #333;
			display: block;
			font-family: Helmet, Freesans, sans-serif; /* bbc glue font stack /*
			font-size: 1.3em; /* only use ems for font-sizes (including on the body) */
			padding: 5px 0 2% 0;
			-webkit-transition: all 700ms ease; /* use ms for duration */
			-moz-transition:    all 700ms ease;
			-ms-transition:     all 700ms ease;
			-o-transition:      all 700ms ease;
			transition:         all 700ms ease;
			z-index: 3;
		}

		.action a {
			color: rgba(0, 0, 0, .2);
		}

###Structure of a style

Use "semi-expanded" structure.

		[selector][comma][carriage-return]
		[selector][space][open-curly-bracket][carriage-return]
		[tab][property][colon][space][property-value][semi-colon][carriage-return]
		[close-curly-bracket][carriage-return]
		[carriage-return]

###Selector naming

* Use only lowercase.
* Use only hyphens to separate words.

###Property order
* Alphabetical.
* By the length of prefix (long to short) for vendor prefixed properties.
* Carry on the alphabetical order for multiple properties (e.g. border-bottom, border-left...):

		.download {
			border-bottom: 1px solid #000;
			border-left: 2px solid #000;
			border-right: 1px solid #000;
			border-top: 2px solid #000;
		}

###Property value order

		background: [colour] ["url"] [scroll] [repeat] [position];
		border: [size] [type] [colour];

###Prefixed Property value spacing

		.download {
			-webkit-transition: all 700ms ease;
			-moz-transition:    all 700ms ease;
			-ms-transition:     all 700ms ease;
			-o-transition:      all 700ms ease;
			transition:         all 700ms ease;
		}
				
###Text formatting

* Use consistent, version-control-friendly text formatting:
	* Use tabs for indentation - length of 4 spaces.
	* Use UNIX-style line endings.
	* Trim trailing whitespace from lines.
	*Ensure all text-based files end with a newline character.

###Media assets naming conventions

* Use only lowercase.
* Use only hyphens to separate words e.g. "home-logo.png".

##Development Guidelines

###Foundation

Use HTML5 Boilerplate as a foundation:
* Use modernizr.
* Use the non-semantic helper classes:
	* Use the class="clearfix" approach to clearing floats.
	* Use the image replacement and text hiding classes.
* Adhere to the W3C's Mobile best practises on every project.
* Use polyfills.
* Use HTML5 semantic tags e.g. sectioning and form elements.
* Use Microformats and HTML5 microdata.
* Use WAI-ARIA landmark roles - see this blog post for more information. Never use ARIA roles to target CSS styles.
* Place all Javascript before the closing </body> tag, except modernizr.
* Use Classes over IDs with the exception of:
	* In-page navigation.

With the following exceptions:

* Use an IE conditional class and "safe hacks".
* Order the <head> as follows:
	1. <meta>
		1. Charset first.
		2. Then alphabetically ordered.
	2. <title>
	3. <link>
	4. <script>

###CSS

Structure of a stylesheet

1. fonts (including url to licence)
2. normalise html5
3. default styles (based on boilerplate/normalise)
	1. html
	2. body
	3. links: a, a:hover, a:active, a:visited
	4. sectioning content: aside, article, nav, section
	5. heading content: h1 – h6, hgroup
	6. text-level semantics: address, blockquote, code, em, pre, strong
	7. grouping content
		1. lists: dl, dt, dd, ul, ol, li
		2. paragraphs
		3. tables: table, thead, tr, th, tbody, td
	8. form content: form, fieldset, legend, label, input, textarea, select, option
	9. embedding content: audio, canvas, embed, iframe, img, object, video
4. helper classes (non-semantic)
5. shared states
6. style patterns: ordered by complexity
7. layout patterns (non-semantic)
8. @media queries
	1. device width (linearised content first)
		1. default styles (based on boilerplate/normalise)
		2. helper classes (non-semantic)
		3. shared states
		4. style patterns: ordered by complexity
		5. layout patterns (non-semantic)
	2. print

####Comments and indentation

Comment within a stylesheet to aid other developers.

* Title
* Colour swatch
* Index
* Sectioning comments
* Property comments

		/*
		 * standards and conventions
		 *
		 * colour swatch:
		 * light blue = #005
		 * dark blue = #00C
		 *
		 * index:
		 * 1. fonts
		 * 2. normalise html5
		 * 3. default styles (based on boilerplate/normalise)
		 * 4. helper classes (non-semantic)
		 * 5. shared states
		 * 6. style patterns
		 * 7. layout patterns (non-semantic)
		 * 8. @mediaqueries
		 */

Use indentation and comments to section a stylesheet. There are two types of comments:

1. Sectioning comments.
2. Property comments.

		/* sectioning comment e.g. "header" */
			header {
				margin: 0;
			}

			/* sectioning comment e.g. "primary navigation" */
				header nav {
					float: left;
				}

			/* sectioning comment e.g. "search box" */
				header search {
					display: inline; /* property comment e.g. ie double margin fix */
				}

###Selector naming

* Use:
	* Plurals for groupings.
	* Nouns for specific objects.
	* Adjectives (where possible) or verbs for variations
	* Past-participle verbs for states.
	* The following for pattern parts:
		* <pattern name>–inner → for inner wrapper
		* <pattern name>–item → for the most common and repeating element in the pattern
		* <pattern name>–content → for containing both media and text
		* <pattern name>–media → for targeting imgs, swf, video
		* <pattern name>–copy → for containing only text e.g. headings and paragraphs

* Do not mimic tag names when naming classes, unless they are prefixed. e.g. .component-body.

		.actions (grouping - plural)
			.action (pattern - noun) .action-collapse (sub pattern - verb)
				.action-inner (pattern part)
					.action-item (pattern part)
						.action-content (pattern part)
							.action-media (pattern part)
							.action-copy (pattern part)

		.folder .is-collapsed (state - past participle)

###Progressive enhancement in CSS

####Modernizr

* Use forward-facing support (i.e. assume feature support and target lack of with the "no-" classes) with the exceptions of:
	* JS → assume no JS and target support with the "js" class.
	* Touch → assume a no-touch device and target support with the "touch" class.

####Backgrounds (language feature)

		.text-area {
			background: url("/images/background-000-50.png") repeat; /* IE fix */
			background: rgba(0, 0, 0, 0.5);
		}

* Start with fall back definition to support older browsers.
* Implement newer definition last.

###Fonts and Font Face

Use tweaked (letter/word spacing etc) web-safe fonts first. Then webfonts, but sparingly, with the following caveats:

* Ensure the font is correctly licensed. Find a licence using a webfont service.
* Ensure the rendering quality of the font is acceptable in all browsers.
* Ensure acceptable loading times are maintained as fonts are added.
* Ensure the correct font weights are included and linked correctly.

##Media assets

###File structure

* Limit of 10 files per folder before subfolder is created
* All vendor/3rd Party scripts to be found in "/vendor" including all assets.
* Creation of child folders within structure below are on a per project basis

		/assets
			/fonts
			/images
				/sprites
					vignettes.png
				background.jpg
				spacer.gif
			/scripts
				project.js
				jquery.standout.js
			/styles
				project-name.css
			/swfs
			/vendor
				jquery.js
				modernizr.js
				/fancybox
				jquery.scrollTo.js

###Images

####Spritesheets

Use spritesheets only for grouped sets of icons.

####Image Formats

* Use JPEG for photos and complex images/icons.
* Use PNG 8 for small and simple images/icons.
* Use PNG 24 for multi-channel transparency.

##Accessibility

* Adhere to the WCAG Samurai checklist.
* Do not check using accessibility validators.

Development Process

Annotate designs to:
Identify a colour palette.
Identify the "base styles" using a "typography-first" approach:
Identify the body copy (the most common block of copy) and its following properties:
Font family.
Font size.
Line height.
Identify text-based grouping elements (and their box models):
Paragraphs.
Lists.
Heading groups.
Identify six levels of headings.
Identify form elements
Legends.
Labels.
Inputs.
Identify style patterns, subpatterns and pattern parts (starting with most common and smallest first):
Actions
Navigation
Content blocks
etc...
Identify layout patterns:
Grids
Positioning
etc...
Identify animation patterns:
Colour transitions (e.g. on simple links)
Show & hide (e.g. reveals, slides, fades)
etc...
Identify interaction patterns:
Clicks
Drags
Hovers (including simple links)
etc...
Produce a draft mapping of the relationships between patterns in each set.
Build a toolkit:
with the following sections:
Base styles
Demo of style patterns.
Demo of layout patterns.
Demo of animation patterns.
Demo of interaction patterns.
Components built from the patterns.
and with the following features:
Self-annotating and with common language between design and development.
A reference for default typography, padding, margin etc.
Built-in relationship mapping.
Testable.
A few notes on the why...

A collection of best practise standards from around the web and for our specific project needs.
This work is licensed under a Creative Commons License by the contributors.