# Markdown Cheatsheet

Text entered on multiple lines in your editor will appear on a single line in your markdown doc. You must entered two carriage returns for markdown to create a new paragraph.

For example, the words "one", "two", "three", and "four" below are entered on separate lines in the text editor, but they appear on a single line in markdown:

one
two
three
four

If the words are entered with two carriage returns, they appear on separate lines in Markdown:

one

two

three

four

### Bold and Italics

Surrounding text with asterisks or underscores will _italicize_ or **bold** the text. A single _asterisk_ or _underscore_ on either side of the text will italicize it, and two **asterisks** or **underscores** on either side bolds the text.

This can be confusing. I follow a convention suggested by Wes Bos, and that is to always use **double asterisks** for bold and _single underscores_ for italic.

### Strikethrough

Surround text with ~~double tildes~~ for strikethrough.

## Headers

Starting a line with one or more hashes will create headers. One hash "#" followed by a space and text creates an H1, two hashes for an H2 and so on.

Examples:

# This is an H1

## This is an H2

### This is an H3

#### This is an H4

##### This is an H5

Note that you do **_not_** need two carriage returns after a header to begin a paragraph on the next line.

Also note that the H1 has a horizontal rule underneath it.

And what I think is my final note regarding headers: you can create an H1 and and H2 by using double-underscores (the equals sign) for an H1 and underscores (the underscore sign, naturally) for an H2. You need to underline the header with at least 3 of these charaters to get it to work. I recommend not using this method to create headers -- use the hash instead, as it works for headers of all weights.

## Links

Turning any url into a clickable link is easy. Just wrap it in angle brackets.

http://www.stonegiantstudio.com

If you want to create a link that has clickable descriptive text, put the text in square brackets before the link in parens.

[A plethora of technical questions and answers](http://stackoverflow.com)

_Did you say "plethora" jefe?_

You can also add a tooltip by including text in quotes after the url:

[Twitter](http://twitter.com "Follow the world in what used to be 40 character chunks")

If your urls are long, and you don't want to include them inline, you can refer to a key anywhere in your document. By convention, simply number the keys. You "join" the url to the clickable text by appending another set of square brackets with the key, then setting up the key elsewhere in your document.

For example:

If you are interested checking out Jon Crowell's public commits, explore his [vast array of repos][1].

Another benefit of using the key is that you can refer to the url multiple times in your document. Remember to [check out Jon's repos][1] at your leisure.

# Images

Images are almost the same as links, but have a bang prefix.

It is possible to link to an image without alternate text, but resist the urge. Blind users won't get any benefit from that approach, so avoid it.

Picture with alternate text:

![Sweet Picture](http://unsplash.it/500/500?random)

Picture with both alternate text and a tooltip:

![Sweet Picture](http://unsplash.it/500/500?random "This is a tooltip for this picture")

You can also use a key, just like a regular link:

![Was this a fort?][2]

### Linking thumbnails to full-size images

This technique works for any two images, but is useful in the case that you want to set up a thumbnail that can be clicked to display a larger version fo the image.

Take the following two links, that are different sizes of the same image:

50 pixel square: <http://unsplash.it/50/50?image=1000>

750 pixel square: <http://unsplash.it/750/750?image=1000>

Set the clickable image as the "link" part of the image link and the target larger image as the url:
[![Cross on mountain: click to see larger](http://unsplash.it/50/50?image=1000)](http://unsplash.it/750/750?image=1000)

Note that you can also use normal markdown inside of the alt-text brackets if you prefer:
[![<img alt="Cross on mountain: click to see larger" src="http://unsplash.it/50/50?image=1000"](http://unsplash.it/750/750?image=1000)

[1]: https://github.com/jonrcrowell?tab=repositories
[2]: http://unsplash.it/500/500?image=101
