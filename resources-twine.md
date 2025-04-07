# Twine resources

- [Twine basics](https://twinery.org/reference/en/getting-started/basic-concepts.html)
- [Twine cookbook](https://twinery.org/cookbook/)
- [Harlowe manual](https://twine2.neocities.org/)

## Prerequisites
 
Install GitHub Desktop, open it and connect it to your GitHub account. Ideally use Twine locally so you don’t lose any of your work.

### Install

- [GitHub Desktop](https://desktop.github.com/)
- [Visual Studio Code](https://code.visualstudio.com/) - please also install the "GitHub Copilot" extension and the "Live Server" extension
- [Twine for Desktop](https://twinery.org/)

### Accounts

Make sure you have set up accounts on the following sites.

- [GitHub account](https://github.com/)

## Create and Publish a Twine Story

### Set Up a Local Repository

To save a history of your changes to your story and to allow you to easily publish it online you will need to set up a repository.

1. Create a local folder/directory for all your projects on your computer. Every time you start a new repository you will want to create it in this folder. Since you will use this folder a lot over the semester, you will ideally locate it on your computer desktop. Call it anything you like but easy to find like `digital-writing-projects`. Make sure there are no spaces in the folder name and use lowercase.
2. Go to GitHub Desktop and create a new repository. Give it the name `digital-writing-twine` (no spaces) and for the "Local Path" select the `digital-writing-projects` folder you created on your desktop in the previous step. Select the "Initialize this repository with a README" checkbox and click "Create Repository".

### Create a Twine Story

In Twine you will need to create a story, add a passage and save the commit in GitHub Desktop.

1. Open Twine and select "+ Story". Call the story anything you want.
2. An "Untitled Passage" will be present. Double-click on the passage.
3. Change the title from "Untitled Passage" to another name and edit the passage content. Close the passage.
4. Select "Build" from the menu at the top to show the build options.
5. Select "Publish to File" and navigate to the repository that you created. There should only be a "README.md" in the directory. Save your file as `index.html` (this is very important as when the story is published on Vercel or Netlify it will make it easier to navigate to).
6. Go to GitHub Desktop and your repository should show changes. Add the comment "Add first passage" where "Summary (required)" is shown and click "Commit to main".

### Add Another Twine Passage

Add one more passage to Twine.

1. Go back to your Twine story and open the first passage by double-clicking on it.
2. Select the text you want to link to the next passage and put two square brackets on either side. So if the text is "You are sitting in a park" and you want the link to be the word "park" the edited text should look like "You are sitting in a [[park]]" and then close the passage.
3. A second passage should now appear. Double-click on the second passage and add text to the passage.
4. Select "Publish to File". Select the `index.html` in your Twine story folder and save over it.
5. Go to GitHub Desktop and your repository should show changes. Add the comment "Add second passage" where "Summary (required)" is shown and click "Commit to main".

### Publish to GitHub

Publish your repository to GitHub.

1. Go to GitHub Desktop and in the top row select "Publish repository".
2. Uncheck "Keep this code private" (this should be public so that it can be part of your folio).
3. Click "Publish Repository".
4. Go to GitHub in your web browser and confirm that the repository is there, including an `index.html` file.

### Deploy Via GitHub Pages

We now use the repository on GitHub to deploy the site with GitHub pages.

1. Go to "Settings" on your repository for your work on GitHub.
2. Click on "Pages" in the sidebar under the section "Code and automation".
3. Under the "Branch" heading on the "GitHub Pages" page change "None" to "main".
4. Leave "/(root)" selected and click "Save".
5. Your project will deploy and a link to your project will be available on the "GitHub pages" page of your repository. You may need to refresh the page for it to appear and it may take a few minutes.

Your Twine story should now be published. Every time you make a change, save over the `index.html`, commit the change and push to GitHub your Twine story will be published though this may take up to 10 minutes before the changes are visible.

## Extend the Twine Story

### Trigger text to change on click

1. Let's start with using the sample text "I dream of cats"
2. If you want to change it to "I dream of horses" you would follow the sentence with `(click-replace: "cats") [horses]`
3. Then if you want the reader to click again and replace "horses" with "turtles" you will add `(click-replace: "horses") [turtles]`
4. Your code would then read `I dream of cats. (click-replace: "cats") [horses] (click-replace: "horses") [turtles]`
5. If you want the original sentence "I dream of cats" to change to "I dream of cats and horses" you would add after the original sentence `(click-append: "cats") [ and horses]`. Notice how we put a space before the words "and horses" so it doesn't come out as "catsand horses"
7. Along with `click-append`, `click-prepend` is another option you can play with

### Text transition delay and effects

If you would like a line of text to appear after a specified transition delay, you can specify how long til you want the transition to take place AND the type of transition, using a plus sign inbetween.

Transition options include `fade-down`, `flicker` and others.

After you specify the length of the transition and type of transition you put the affected text in square brackets like this:
`(t8n-delay: 5s) + (t8n: "fade-down") [your words go here]`

### Add an Image to a Passage

1. Create a folder titled `images` in the same folder as the `index.html` file.
2. Add the image for your Twine story to that folder.
3. In your Twine story add an image element with a relative reference to your image file. So if your image is called `example.jpg` add the following image element:
   ```html
   <img class="story-image" src="./images/example.jpg" alt="an example" />
   ```
4. You'll notice that even when you save your changes and push them to GitHub, there is some lag time in being able to properly view the image. You can get an instant preview when you are in GitHub Desktop by clicking "Open in Visual Studio Code". If you don't see this option, then in your GitHub Desktop settings, under "Integrations", make sure your External Editor is set to Visual Studio Code. Once you open VS Code, right click on the `index.html` file and click "Open with Live Server" and you will get an accurate preview of your website in your web browser. You can also click "Go Live" at the bottom of the screen. If you are having an issue with getting this step to work, make sure that in Visual Studio Code you have installed the "GitHub Copilot" and "Live Server" extensions

### Change the Story Stylesheet 

This process is similar to editing CSS.

1. In the top menu of Twine click "Story" to reveal the menu options for your story
2. Select "Stylesheet"
3. Add styles for the story including font and background colour, style images and links, and add padding to address the issue of always having to scroll down to read the text

Paste this code into the Stylesheet to start with:

```css
@import url('https://fonts.googleapis.com/css2?family=Homemade+Apple&display=swap');

tw-story {
  font-family: 'Homemade Apple', cursive;
  color: #FFF;
  background-color: #000;
}

.story-image {
  width: 100%;
}

tw-link, tw-link:link, tw-link:visited, tw-link.visited {
  color: #FFF;
  text-decoration: underline;
}
tw-link:focus, tw-link:hover, tw-link:active, tw-link.visited:hover {
  color: #FFF;
  text-decoration: none;
}
tw-passage {
  padding-bottom: 200px;}
```
4. Now import fonts of your choice from [Google fonts](https://fonts.google.com/) and change the `font-family` property

### Adding a Linked Image

1. [Add an image to the passage as shown in the earlier Add an Image to a Passage exercise](resources-twine.md#add-an-image-to-a-passage)
   ```html
   <img class="story-image" src="./images/example.jpg" alt="an example" />
   ```
2. Treat the image HTML the same as link text in a Harlowe link. So if the passage you are linking to is called "Another room", in your passage you would have:
   ```html
   [[<img class="story-image" src="./images/example.jpg" alt="an example" />->Another room]]
   ```

### Adding Audio

1. Create an `audio` folder/directory in the same folder/directory as the `index.html`.
2. Add the sound file for your Twine story to that folder/directory.
3. In your Twine story add an audio element with a relative reference to your sound file. So if your sound file is called `example.mp3` add the following audio element:
   ```html
   <audio src="./audio/example.mp3" autoplay loop></audio>
   ```

## Image properties in Twine

### Scaling Images

In-text images can be scaled in different ways.

#### Scaling All Images

If you want to scale all images the same way it is easiest to apply the scaling to the image element.

To scale all images to 100% of the passage width:

1. Open "Story"->"Stylesheet" from the menu
2. Add the following:
   ```css
   img {  /* this selects all image (img) elements */
     width: 100%;
   }
   ```

#### Scaling Images by Class

If you want to scale only certain images or sets of images in different ways it is best to use a class. Classes are more specific than targeting the element which means you can have 100% set for all images and use a class to set another width for other images.

To add a class which scales an image to 50% of the passage width:

1. Open "Story"->"Stylesheet" from the menu
2. Add the following:
   ```css
   .story-image-smaller {  /* this selects all elements with the story-image-smaller class not just images */
     width: 50%;
   }
   ```
   Or
   ```css
   img.story-image-smaller {  /* this selects all images with the story-image-smaller class */
     width: 50%;
   }
   ```
3. Open the passage with the image
4. Add the class to the image. If you have the following image in a passage:
   ```html
   <img src="./images/example.jpg" alt="an example" />
   ```
   When you add the class it will be:
   ```html
   <img class="story-image-smaller" src="./images/example.jpg" alt="an example" />
   ```

#### Scaling Images with Style

If you want to scale all the images in different ways it is probably still better to use classes or ids to select them but you can also directly apply styles to the image element. The style attribute is more specific than targeting the class or element so it will take precedence over those.

To change the width of a specific image to 30% of the passage width:

1. Open the passage with the image
2. Add a style attribute with the style to the image. If you have the following image in a passage:
   ```html
   <img src="./images/example.jpg" alt="an example" />
   ```
   When you add the style it will be:
   ```html
   <img style="width: 30%;" src="./images/example.jpg" alt="an example" />
   ```

### Images with the CSS Grid Layout

A simple way to show images is to use the CSS grid layout.

To use the grid layout to display an image to the right-hand side of the text:

1. Open the passage
2. Add the text "This is example text" and the image:
   ```html
   <img src="./images/example.jpg" alt="an example" />
   ```
3. Add `div` elements with the class (as shown) around the text and image:
   ```html
   <div class="story-room"><div class="story-text">This is example text.</div><div class="story-image"><img src="./images/example.jpg" alt="an example" /></div></div>
   ```
4. Open "Story"->"Stylesheet" from the menu
5. Add the following:
   ```css
   .story-room {
     display: grid;  /* sets the display to grid on the surrounding div */
     grid-template-columns: 50% 50%;  /* sets each column to 50% */
   }
   .story-text {
     grid-column: 1;  /* sets which column the text appears in */
     grid-row: 1;
     box-sizing: border-box;
     padding: 10px;
   }
   .story-image {
     grid-column: 2;  /* sets which column the image appears in */
     grid-row: 1;
   }
   .story-image img {
   max-width: 100%;
   height: auto;
   display: block;
   }
   ```

If you want the image to appear on the left and the text on the right, then swap the values for `grid-column`.

### Background Images Using Tags

To set per passage background images in Twine we can use tags on the passage and then use these tags to set the background image where a passage is tagged.

1. Add the intended background image to the images folder like in the [earlier Add an Image to a Passage exercise](resources-twine.md#add-an-image-to-a-passage)
2. Select the passage for the background image
3. Below the passage name select the "+ Tag" button and add a tag called "example-background" (the tag can be called anything so long as there are no spaces)
4. Open "Story"->"Stylesheet" from the menu
5. Add the following styles to show the background image (in this example we expect a background image called `background-example.jpg`)
   ```css
   tw-story[tags~="example-background"] {  /* the tag added in step 2 */
     background-image: url(./images/background-example.jpg);  /* the image added in step 1 */
     background-size: cover;  /* cover the whole element */
     background-repeat: no-repeat;  /* do not repeat the background image */
   }
   ```

## Image Maps
**Follow this [guided video instruction](https://www.loom.com/embed/8ec5d97f6c1c4683adec6439049d33f2?sid=f0d64dfd-6e97-484c-9383-fd4b16670fdc) to assist you in completing a basic image map in Twine**

### Prerequisite

1. Make sure you have your Twine set up with the passages already created. This project should be saved to an `index.html` file within a designated `image-map` folder within your main `digital-writing-project` file. Keep the names of the passages simple as you will use them when setting up your image map. **IMPORTANT NOTE: When you commit your changes for the first time using GitHub Desktop, make sure to set up a new repository so that you do not overwrite your previous repository.** 
2. Have an image ready for the image map, and place it in an `images` folder within your `image-map` folder. Preferably you will resize the image in advance so that it is not too large in spatial dimensions or megabites.

### Creating an Image Map

1. Upload your image to the [Image Map Generator](https://www.image-map.net/)
2. Create an area on the map for each of the passages you want linked. For each area choose the shape you want (if it is irregular then you will want to select "Poly")
3. For each area leave "Link" and "Target" blank and ensure that "Title" has the name of the passage you want linked.
4. Select "Show Me The Code!" and copy the code shown and paste it into the passage with where you want your image.
5. Update the `img` tag on the page and ensure it is pointing to your image by changing the `<img src>` to `<img src="./images/example.jpg" usemap="#image-map">`, replacing the word "example" with your image file name.

### Linking the Image Map

1. You can either copy the lines of code from our repository's [Harlowe script resourse file](/resources-twine-harlowe-script) or else download the latest [`harlowe-macro-api.zip` from Chapel's Unofficial Custom Macro Framework for Harlowe](https://github.com/ChapelR/harlowe-macro-api/releases) and copy the contents of the `macro.js` file.
3. Paste the copied contents into your Twine story JavaScript (Story->JavaScript).
4. To the bottom of the passage with your image map add:
   ```html
   <script>
    $('area').on('click', function(e){
	  e.preventDefault();
	  Harlowe.goto(this.alt);
    });
   </script>
   ```

### Scaling the Image Map

1. Copy the [contents of the Image Map Resizer](https://raw.githubusercontent.com/davidjbradshaw/imagemap-resizer/master/js/imageMapResizer.min.js) to the top of your Twine story JavaScript (Story->JavaScript).
3. Update the script element at the bottom of the passage with your image map to:
   ```html
   <script>
    $('area').on('click', function(e){
	  e.preventDefault();
	  Harlowe.goto(this.alt);
    });
    $('map').imageMapResize();
   </script>
   ```
### Hiding the passage links

To hide the targeted passage links - these are the links to the new story "rooms" which are enclosed within two sets of square brackets - wrap your targeted passages within the following `div` tags:

```
<div style="display:none;"
[[head]]
[[middle]]
[[legs]]>
</div>
```

### Publishing your image map

After you push your commits to GitHub using GitHub Desktop, navigate to your GitHub repository online and publish via GitHub pages.

## How do you show background videos in Twine?

Adding a background video to a Twine passage is similar to adding audio or a foreground image. First, add a `video` directory to your Twine project directory (much like you have for audio and images). Then add the video file to the `video` directory. For instance, if you have a video called `video.mp4` you would add it to the `video` directory. As we are using GitHub the file cannot be larger than 25MB. If it is larger than this you will need to cut or compress the video.

Once you've added the video to your video directory, add the following to the passage in which you want the video to appear (update the filename to the name of your video):

```html
<video autoplay loop muted class="background-video">
  <source src="video.mp4" type="video/mp4">
</video>
```

That will show the video inline with the text. As we want to show the video in the background we need to adjust the styles. Add a tag to the passage called `video`. We will use that tag to change the styles on the passage where we want the video to appear in the background. Then add the following to your Twine Story Stylesheet (Story->Stylesheet):

```css
/* Style the background where the video will appear */
tw-story[tags~="video"] {
  background-color: transparent;
}

/* Style the video element */
.background-video {
  position: fixed;
  right: 0;
  bottom: 0;
  min-width: 100%; 
  min-height: 100%;
  z-index: -100; /* Place the video behind everything */
}
```

## How can you use different fonts on different passages in Twine?

First select all the fonts you want to use in your piece from [Google Fonts](https://fonts.google.com/). For each font you click on select "Get font". When you've picked all the fonts you want to use select "Get embed code". From that screen select "@import" and copy the text **between** `<style>` and `</style>` into your Twine Story Stylesheet (Story->Stylesheet).

For instance, if I wanted to use Libre Baskerville, Oswald, and Jacquard 12, I would select each font and when the final font was selected I would click "Get embed code". After selecting "@import", I would copy the following to the top of my Twine Story Stylesheet:

```css
@import url('https://fonts.googleapis.com/css2?family=Jacquard+12&family=Libre+Baskerville:ital,wght@0,400;0,700;1,400&family=Oswald:wght@200..700&display=swap');
```

To apply a different style to specific passages follow the base [instructions for adding background colours to passages using tags](./exercises/week8/#background-images-using-tags). Instead of changing the background image the font is changed. For my example fonts, Libre Baskerville and Jacquard 12 are static fonts and Oswald is a variable font. To apply a static font I can copy the suggested style into the stylesheet for the specific tag. So for Libre Baskerville I would add the following, for the tag `night`:

```css
tw-story[tags~="night"] {
  font-family: "Libre Baskerville", serif;
  font-weight: 400;
  font-style: normal;
}
```

For Oswald, a variable font, I need to replace the `<weight>` with a weight (how bold the font is) that I want to use. The options given for Oswald vary between 200 to 700. To match the weighting I've used for Libre Baskerville, I'll select 400. So for Oswald I would add the following, for the tag `day`:

```css
tw-story[tags~="day"] {
  font-family: "Oswald", sans-serif;
  font-optical-sizing: auto;
  font-weight: 400;
  font-style: normal;
}
```

The fonts then should appear as expected in the Twine passages with the tags `night` and `day`.

## How to Add a Proof for Twine Stories

1. Select "Build" on the Twine menu
2. Select "Proof" which will open the proof in the browser
3. From your browser select "Save Page As"
4. Navigate to your project directory/folder
5. Save the file as `proof.html` in the same directory as your `index.html`
