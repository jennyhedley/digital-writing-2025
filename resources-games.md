# Games

## Bitsy

Bitsy is a web-based games designer on itch.io by Adam Le Doux. Best for tiny adventures, short narrative games or vignettes, games appear in lo-res, 8-bit style, with only three colours permitted in each room’s colour scheme - two background colours and another for avatars, items and sprites/NPCs. 

**This quick [Bitsy video tutorial](https://www.loom.com/share/e02adc5163c8433fa6a99305d3ffc010?sid=41bf6ce5-732b-4c10-ba5f-ab476249e843) will take you through the steps in the instructions below.**


### Create a Bitsy Game

1. Open GitHub Desktop and create a new repository for your Bitsy game
2. Go to the [Bitsy Game Maker](https://ledoux.itch.io/bitsy)
3. Select "Run tool"
4. There are a lot of different things that you can do with Bitsy so look at this [Bitsy tutorial](https://www.shimmerwitch.space/bitsyTutorial.html) and make some changes to your Bitsy game
5. Select "download game" depending on your browser set up this will either download the file to where that is configured or give you a choice
   - If given a choice save it as `index.html` in the repository you created in step 1
   - Otherwise, find where it has downloaded to and copy it as an `index.html` into the repository you created
6. Commit the change
7. Push to GitHub

### Publish the Game with GitHub Pages

1. Go to "Settings" on your repository for your work on GitHub.
2. Click on "Pages" in the sidebar under the section "Code and automation".
3. Under the "Branch" heading on the "GitHub Pages" page change "None" to "main".
4. Leave "/(root)" selected and click "Save".
5. Your project will deploy and a link to your project will be available on the "GitHub pages" page of your repository. You may need to refresh the page for it to appear and it may take a few minutes.

### Bitsy resources

- [Bitsy](https://ledoux.itch.io/bitsy)
- [A Bitsy Tutorial](https://www.shimmerwitch.space/bitsyTutorial)
- [Dan Cox's Bitsy tutorial](https://videlais.com/2018/04/06/bitsy-4-tutorial-videos/)
- [YouTube tutorial - More complex sprite interactions, using dialogs](https://www.youtube.com/watch?app=desktop&v=pbz1hWEJelc)
- [Bitsy Games Wiki](https://bitsy.fandom.com/wiki/Bitsy_Wiki)
- [Bitsy hacks]( https://github.com/seleb/bitsy-hacks) – scripts to enable additional Bitsy functionality

### Bitsy tutorial and example

- [YouTube tutorial](https://www.youtube.com/watch?v=SJtuDQuZvQY) by DatJuanDesigner
- [Why did the chicken cross the road? game](https://juegos.itch.io/why-did-the-chicken-cross-the-road) by DatJuanDesigner

### More Bitsy examples

- [Top Bitsy games](https://itch.io/games/tag-bitsy)  
- [Stand Up](https://backslashlit.com/issues/6/rae-white) by Rae White
- [You are Dough](https://npckc.itch.io/you-are-dough) by npckc
- [The Mountain is as it Always Was](https://cxmi.itch.io/the-mountain) by Christine Mi – CW themes of grief
- [Under a Star Called Sun](https://haraiva.itch.io/under-a-star-called-sun) by Cecile Richard – CW themes of grief
- [Endless Scroll](https://www.voiceworksmag.com.au/all/2019/12/18/endless-scrolls) by Cecile Richard – CW themes of grief
- [Commute](https://thisisstar.itch.io/commute) by Star St. Germain


### Additional Bitsy recommendations and info from Mollie

Some Bitsy pieces I like!
- https://cxmi.itch.io/the-mountain Links to an external site.
- https://haraiva.itch.io/under-a-star-called-sun Links to an external site. 
- https://haraiva.itch.io/endless-scroll Links to an external site.  
- https://haraiva.itch.io/i-am-still-here Links to an external site. 
- https://caeth.itch.io/reunion Links to an external site.
- https://princessinternetcafe.itch.io/breathe Links to an external site. 
- https://communistsister.itch.io/decay Links to an external site. (combination of Bitsy and Twine!)

Where to find more!
- https://itch.io/games/tag-bitsy Links to an external site. 

Also, Mollie made a [discord server](https://discord.gg/HEmnrkEBGZ) for the class, come say hi!

## Inform 7

Whereas Twine facilitates hypertext narratives where you progress through the story by clicking on links, Inform requires the reader to type commands to interact with the story.

**This quick [Inform video tutorial](https://www.loom.com/share/f51ed2514a8d404c9e4902d5e52f1fe6?sid=00e497ba-1f32-4ea1-a5c9-127198d29a86) will take you through the steps in the instructions below.**

### Inform resources

- [Inform 7](https://ganelson.github.io/inform-website/) – requires download
- [Inform 7 documentation](https://intfiction.org/t/inform-7-documentation-and-resources/3311)
- [Inform wiki](https://www.ifwiki.org/Inform_7)
- [YouTube tutorial](https://www.youtube.com/watch?v=bTdoFHTxQRI&list=PLIbbXV3eCGNq8pZ2BK58V4gPyYSji19HE) by Zoroarrkk


### Download Inform

1. Go to the [Inform 7 releases page](https://github.com/ganelson/inform/releases) and download a copy of Inform.

### Create an Inform 7 Story

1. Create a repository on [GitHub](https://github.com/) with a `README.md` file
2. Add a new file to the repostitory called `.gitignore` and add the following contents:
   ```
   # mac
   .DS_Store

   # inform
   *Build
   *Index
   *.plist
   *.blurb
   *.rtf
   *.iFiction
   *.skein
   ```
3. Commit the change
4. Clone the repository locally with [GitHub Desktop](https://desktop.github.com/) by selecting "File" -> "Clone Repository" and choosing your repository from the list
5. Open Inform 7 and create a new project and call it `Example`
6. Save the project in your repository directory
7. Add some text to the file leaving the name of the project and your name where Inform adds it. Make sure to include "Release along with an interpreter." on the line between your story title and the story text:
   ```
   "Story title" by Your name

   Release along with an interpreter.

   The Living Room is a room. West is The Kitchen. The Living Room has the description "The room is well lit."

   The Kitchen is a room. The Kitchen has the description "This is where we cook."
   ```
8. Click "Go!" to test - Tip: If you type `go west` at the position of the blinking cursor, the story will reveal The Kitchen
9. Click "Release" to release
10. Commit the change
11. Push to GitHub - note this can't be published as is via GitHub pages because there is no index.html file, but people can download a zipped file of your game and import it into the Inform desktop software

#### Adding a Cat to the Living Room

```
The cat is an animal in the Living Room. The printed name of the cat is "a fluffy cat".

Understand "pet [something]" and "stroke [something]" as petting.

Petting is an action applying to one visible thing.

Carry out petting the cat:
    say "You pet the cat and it purrs contentedly."

Understand "pick up [something]" and "take [something]" as picking up.

Picking up is an action applying to one thing.

Carry out picking up the cat:
    say "You pick up the cat and it meows softly as it settles into your arms.";
    move the cat to the player.
```

### Additional game resources

- [Directory of open source, experimental and tiny tools](https://tinytools.directory/) 

#### GameMaker platform and example
- [GameMaker](https://gamemaker.io/en) – requires download
- [Touch Melbourne](https://gleeson.itch.io/touchmelbourne) by Andrew Gleeson and Cecile Richard

#### Visual Novel games
- [Ren’Py](https://www.renpy.org/) – a “visual novel engine” – requires download
- [Visual Novel Database](https://vndb.org/v?q=&ch=&f=05N18fwRen_7Py-N18a5h741N18Ng01N18gwcomplete-&s=n2w) 
- [Top Visual Novel games tagged IF](https://itch.io/games/tag-interactive-fiction/tag-renpy)
