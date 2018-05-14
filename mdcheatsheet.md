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

## Images

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

Note that you can also use normal markdown inside of the alt-text brackets if you prefer, but markdownlint will squawk at you for using inline-html:

[<img alt="Cross on mountain: click to see larger" src="http://unsplash.it/50/50?image=1000">](http://unsplash.it/750/750?image=1000)

## Lists, nesting, bullets and numbers

Unordered lists can be created by prefixing your lines of text with a hyphen, a plus sign, or an asterisk. I used a hyphen as a prefix for these soccer teams, but when I saved my file, prettier or some other plugin converted them to asterisks, which is fine with me.

Best teams of all time:

* Flamengo
* Barcelona
* São Paulo
* Santos
* Conrinthians
* Liverpool
* Ajax
* AC Milan
* Real Madrid
* Juventus
* Manchester United
* Paris Saint Germain

You can create nested lists by tabbing or spacing a bullet to the right. Markdown processors will vary the bullets between different levels.

### World Cup Winners

_Only 8 countries have ever won the World Cup_

* 5 Time Winners
  * Brazil
* 4 Time Winners
  * Germany
  * Italy
* 3 Time Winners
  * Nobody at the moment
* 2 Time Winners
  * Uruguay
  * Argentina
* 1 Time Winners
  * England
  * France
  * Spain

Ordered lists work the way you'd expect them to for the most part, although one really nice feature is that you don't have to specify the order, which means inserting new items or re-ording them is painless. Simply prefix each line by a number, conventionally **1.** and Markdown will take care of the rest.

### Greatest players of all time

1.  Zico
2.  Pele
3.  Maradona
4.  Eusebio
5.  Puskas
6.  Messi
7.  Cristiano Ronaldo
8.  Ronaldinho
9.  Garrincha
10. Beckenbauer
11. Rivelino
12. Platini
13. Zidane

*And no, Beckham doesn't deserve to be on this list, so please don't ask.*
_I'm also aware that Zico is not usually number 1, but it's my list._

Mixing ordered and unordered lists is fine, but you can't include them at the same indentation level.

I'm also not sure how to begin an ordered list at a number other than 1.

## Horizontal Rules

Create a horizontal rule with three or more hyphens, asterisks, or underscores on a line with a line-break above. (If you have them under text without a line-break, they will turn the text into an h1. My formatting plugin prefers hyphens, and I do too.)

---

## Block Quotes

Use the greater than symbol (**>**) prefix to create a block quote.

> Ancora amparo. (_I am still learning._)
>
> -- **Michaelangelo**, when he was 87

## Code Blocks

You can create a code block with either indentation or with back-ticks.

With indentation:

    const dufus = "Homer";
    const beer = "Duffs";
    const add = (a, b) => { a + b };

And with back-ticks, specifying js as the language:

```js
const dufus = "Homer";
const beer = "Duffs";
const add = (a, b) => {
  a + b;
};
```

You can also add a code block in-line by wrapping your code with single back-ticks:

Einstein and Big Audio Dynamite both made the formula `e=mc2` famous.

You can get all records in a table like so: `select * from myTable`

Another cool thing you can do with code blocks that I saw in a Wes Bos video is to specify the language as **diff**. You can then show code that should be deleted with the code that should replace it:

```diff
const x = 100;
- const y = 200;
+ const y = 300;
```

## Tables

Tables in markdown are really cool. Set them up by separating the table cells with pipes, and add field indicators `|:---------|:-----------|` underneath the table header.

| Sport      | GOAT           |
| :--------- | :------------- |
| Soccer     | Zico           |
| Golf       | Tiger Woods    |
| Basketball | Michael Jordan |
| Hockey     | Wayne Gretzky  |

Aligning content in the cells is accomplished by adjusting colons. I'm pretty sure that the previous sentence just guaranteed that this repo will appear in some non-markdown-related search results.

* Left-aligned |:---------|
* Centered |:---------:|
* Right-aligned |---------:|

| State        | Abbreviation                            | Population            |
| :----------- | :-------------------------------------: | --------------------: |
| Texas        | TX                                      | 29,862,596            |
| California   | CA                                      | 39,250,017            |
| Wisconsin    | WI                                      | 5,778,708             |
| Rhode Island | Rhode Island and Providence Plantations | 5,778,708,532,533,143 |

The last row is included to show that the headers follow the same alignment rules as the column below.

[1]: https://github.com/jonrcrowell?tab=repositories
[2]: http://unsplash.it/500/500?image=101
