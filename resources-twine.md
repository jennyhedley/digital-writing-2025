#Twine resources

## Prerequisites
 
Install GitHub Desktop, open it and connect it to your GitHub account. Ideally use Twine locally so you don’t lose any of your work, but you can also use the online version.

### Install

- [GitHub Desktop](https://desktop.github.com/)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Twine](https://twinery.org/)

### Accounts

Make sure you have set up accounts on the following sites.

- [GitHub account](https://github.com/)

## Create and Publish a Twine Story

### Set Up a Local Repository

To save a history of your changes to your story and to allow you to easily publish it online you will need to set up a repository.

1. Create a local folder/directory for all your projects on your computer. Every time you start a new repository you will want to create it in this folder. Call it anything you like but easy to find like `digital-writing-projects`.
2. Go to GitHub Desktop and create a new repository. Give it the name `digital-writing-twine` and for the "Local Path" select the folder you created in the previous step. Select the "Initialize this repository with a README" checkbox and click "Create Repository".

### Create a Twine Story

In Twine you will need to create a story, add a passage and save the commit in GitHub Desktop.

1. Open Twine and select "+ Story". Call the story anything you want.
2. An "Untitled Passage" will be present. Double-click on the passage.
3. Change the title from "Untitled Passage" to another name and edit the passage content. Close the passage.
4. Select "Build" from the menu at the top to show the build options.
5. Select "Publish to File" and navigate to the repository that you created. There should only be a "README.md" in the directory. Save your file as `index.html` (this is very important as when the story is published on Netlify it will make it easier to navigate to).
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
4. Go to GitHub in your web browser and confirm that the repository is there.

### Deploy Via GitHub Pages

We now use the repository on GitHub to deploy the site with GitHub pages.

1. Go to "Settings" on your repository for your work on GitHub.
2. Click on "Pages" in the sidebar under the section "Code and automation".
3. Under the "Branch" heading on the "GitHub Pages" page change "None" to "main".
4. Leave "/(root)" selected and click "Save".
5. Your project will deploy and a link to your project will be available on the "GitHub pages" page of your repository. You may need to refresh the page for it to appear and it may take a few minutes.

Your Twine story should now be published. Every time you make a change, save over the `index.html`, commit the change and push to GitHub your Twine story will be published though this may take up to 10 minutes before the changes are visible.

## Extend the Twine Story

### Add an Image to a Passage

1. Create a `images` folder/directory in the same folder/directory as the `index.html`.
2. Add the image for your Twine story to that folder/directory.
3. In your Twine story add an image element with a relative reference to your image file. So if your image is called `example.jpg` add the following image element:
   ```html
   <img class="story-image" src="./images/example.jpg" alt="an example" />
   ```

### Change the Story Styles

1. In the top menu of Twine click "Story" to reveal the menu options for your story
2. Select "Stylesheet"
3. Add styles for the story, links and change the font

Example styles:

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
```

### Adding a Linked Image

1. [Add an image to the passage as shown in the week 5 exercise](week5.md#add-an-image-to-a-passage)
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


## Images in Twine

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
   ```

If you want the image to appear on the left and the text on the right, then swap the values for `grid-column`.

### Background Images Using Tags

To set per passage background images in Twine we can use tags on the passage and then use these tags to set the background image where a passage is tagged.

1. Add the intended background image to the images folder like in the [add an image to a Twine passage exercise](week6.md#add-an-image-to-a-passage)
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

### Prerequisite

1. Make sure you have your Twine set up with the passages already created or a list of passages. You will use the names of the passages when setting up your image map.
2. Have an image ready for the image map.

### Creating an Image Map

1. Upload your image to the [Image Map Generator](https://www.image-map.net/)
2. Create an area on the map for each of the passages you want linked. For each area choose the shape you want (if it is irregular then you will want to select "Poly")
3. For each area leave "Link" and "Target" blank and ensure that "Title" has the name of the passage you want linked.
4. Select "Show Me The Code!" and copy the code shown and paste it into the passage with where you want your image.
5. Update the `img` tag on the page and ensure it is pointing to your image.

### Linking the Image Map

1. Download the latest [`harlowe-macro-api.zip` from Chapel's Unofficial Custom Macro Framework for Harlowe](https://github.com/ChapelR/harlowe-macro-api/releases).
2. Open `macro.js` and copy the contents into your Twine story JavaScript (Story->JavaScript).
3. To the bottom of the passage with your image map add:
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
