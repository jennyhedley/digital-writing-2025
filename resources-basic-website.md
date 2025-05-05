## HTML, CSS and JavaScript

[HTML/HyperText Markup Language](https://developer.mozilla.org/en-US/docs/Web/HTML)
- Structure
  
[CSS/Cascading Style Sheets](https://developer.mozilla.org/en-US/docs/Web/CSS)
- Presentation (Screen/Print/Audio)

[JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- Behaviour

## Free resources for Learning Web Development

- [MDN Docs Learn Web Development](https://developer.mozilla.org/en-US/docs/Learn)
- [Codeacademy](https://www.codecademy.com/catalog)
- [freeCodeCamp](https://www.freecodecamp.org/)
- [The Coding Train YouTube channel](https://www.youtube.com/channel/UCvjgXvBlbQiydffZU7m1_aw)
- Express Media occasionally runs free [Digital Storytelling workshops](https://www.expressmedia.org.au/programs) for young writers (<25)


## Free P5.js library of animations whose code you can integrate in your website

- [P5.js library](https://p5js.org/libraries/)
- [Random poetry animation example](https://p5js.org/examples/listing-data-with-arrays-random-poetry/)
- [Animated text example](https://editor.p5js.org/radium.scientist/sketches/H6FNGhtU5)

## Create a Simple Website (Free)

- Download [GitHub Desktop](https://desktop.github.com/)
- Download [Visual Studio Code](https://code.visualstudio.com/)
- Create a folder/directory
- Create a new repository username.github.io in GitHub Desktop
- Add the base empty files:
  - index.html
  - css/styles.css
- Add basic HTML to the index.html
- Update the index.html with content such as:
  - Your name
  - Your photo
  - Links to your two remix exercises
  - Publications
  - Artist statement
  - Biography
- Add styles to the styles.css
- Update the styles.css with styles such as:
  - Font
  - Background and text colour
  - Layout changes
 
## Commercial Website Builders/Services

- [WordPress](https://wordpress.com/)
- [Squarespace](https://www.squarespace.com/)
- [Weebly](https://www.weebly.com/au)

## A block of code to display an essay on a web page, preserving formats with `<pre>` tags - you can ignore the error in Glitch

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- import fonts here -->

    <title>Author Website</title>
   <style>
    body {
      background: white;
      color: black;
      font-family: Georgia, serif;
      padding: 4rem;
      margin: 0;
      line-height: 1.6;
    }

    pre {
      white-space: pre-wrap;   /* allows word wrapping inside <pre> */
      font-family: Georgia, serif;
      font-size: 1.1rem;
      background-color: rgba(255, 255, 255, 0.05);
      padding: 2rem;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0,0,0,0.4);
    }
  </style>
</head>
<body>

<pre>
This is the title of the essay

    This is an indented paragraph, written with the original formatting preserved.
    Notice that line breaks and spacing are kept exactly as typed.

    You can still *emphasize text* or use _underscores_ if you like, even if it's
    not semantic HTML — just be consistent with your styling.

Here's another paragraph, without needing <p> tags or inline italics.

        - A bullet point
        - Another bullet point

    The formatting is yours to control.
</pre>

</body>
</html>
```
