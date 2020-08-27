# Tutorials

Step by step tutorials are authored in markdown and automatically converted by the editor. This page describes the format for these tutorials.

For more information, check out [this video](https://www.youtube.com/watch?v=S2V-mLlm-sQ&list=PLMMBk9hE-Serm1gkooPSYGMOaGkGjMZq2&index=47&t=0s) about authoring tutorials.

## Table of Contents

1. [How tutorials work](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#how-tutorials-work)

2. [Tutorial documents](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#tutorial-documents)

3. [Tutorial format](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#tutorial-format)

    * [Metadata](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#metadata) 

    * [Title](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#title)

    * [Activities](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#activities)

    * [Steps](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#steps)

    * [Hints](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#hints)

    * [Images](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#images)

4. [Step modifiers](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#step-modifiers)

    * [fullscreen](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#fullscreen)

    * [unplugged](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#unplugged)
  
    * [tutorialCompleted](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#tutorialcompleted)

5. [Using blocks](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#using-blocks)

   *  [Hint blocks](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#hint-blocks)

   * [Ghost blocks](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#ghost-blocks)

   * [Templates](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#templates)

   * [JRes](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#jres)

6. [Using Python](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#using-python)

7. [Python snippets](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#python-snippets)

8. [Spy snippets (JavaScript to Python)](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#spy-snippets-javascript-to-python)

9. [Other languages](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#other-languages)

10. [Adding tutorials to the home screen](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#adding-tutorials-to-the-home-screen)

      * [JavaScript and Python tutorial ("Spy tutorials")](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#javascript-and-python-tutorial-spy-tutorials)

      * [In-context tutorials](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#in-context-tutorials)

11. [Testing](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#testing)

12. [Example](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#example)

13. [Translations](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#translations)

14. [Dependencies](https://github.com/ksavage-work/minecraft-tutorial/blob/master/minecraft-user-tutorials.md#dependencies)


## How tutorials work

A tutorial is a sequence of steps that the user follows in a limited environment. The experience is designed to reduce the complexity of using the full editor to simply guiding the user through a precise sequence of limited interactions. Tutorials are used as "ramp up" tools to teach both how the editor works and how the basics of blocks work. An editor can have as many tutorials as needed.

Each step of the tutorial has a short description, or explanation, of the activity for the step and
possibly a block example. If the step includes a block example, the editor will restrict the selection of blocks from the toolbox to only those used in the example.

### ~ hint

#### Tutorial tool

You can write, edit, and test a tutorial with the online [Tutorial Tool](https://makecode.com/tutorial-tool). Select the MakeCode editor target that your tutorials is for and then write the tutorial. Run your tutorial to see how it will look in the editor.

### ~

## Tutorial documents

Tutorials are simply markdown documents where each level 2 heading (``##``) is a new step. The tutorials can be located anywhere under the ``/docs`` folder although they usually are in the ``/docs/projects`` folder.

A tutorial with the title '**Light blaster**' would have a path like this: _/docs/projects/light-blaster.md_.

When a tutorial is chosen in the editor, the tutorial runner converts the content of the tutorial markdown into user interactions. If selected from the external documentation navigation, the tutorial is viewed the same as any other help document which allows it to be printed.

### ~ hint

#### A real example

See the Minecraft tutorials [**chicken-rain.md**](https://github.com/Microsoft/pxt-minecraft/tree/master/docs/tutorials/chicken-rain.md) and
[**flower-trail.md**](https://github.com/Microsoft/pxt-microbit/tree/master/docs/tutorials/flower-trail.md).

### ~

## Tutorial format

The tutorial markdown has a format that the guides the tutorial runner in making a sequence of interactions. A tutorial has a flow model that is either a simple set of steps or groups of steps placed into activity sections. The tutorial author chooses which type of flow to use by setting a metadata option.

### Metadata

Tutorial metadata is optionally specified at the top of the document. Metadata is defined as key-value pairs, in the form: ``### @KEY VALUE``. The currrent properties are:

* **activities**: Indicates a three-level tutorial, with activities and steps within the activities. The default is ``false`` which means that the tutorial is just a simple sequence of steps.
* **explicitHints**: Indicates explicit hints, in the format ``### ~ tutorialhint``. The default is ``false`` making hints available for each step.
* **flyoutOnly**: Indicates that the tutorial should display all available blocks in a permanently-visible flyout, instead of the toolbox. The default is ``false``.
* **hideIteration**: Hides the step controls. This includes the previous, next, and exit tutorial buttons, as well as the step counter in the menu bar. The default is ``false``.
* **diffs**: enable/disable diffs on all languages

```markdown
### @activities true
### @explicitHints true
### @flyoutOnly true
### @hideIteration true
### @diffs true
```

### Title

For a step based tutorial, the title is on the first line and uses a _level 1_ heading.


```markdown
# Chicken rain
```

In an activity style tutorial, the title can appear in a psuedo-activity that serves as an introduction. The title is also displayed in the tutorial control bar.

```markdown
### @activities true

## Introduction

### Introduction step @unplugged

![Chicken Rain](/static/tutorials/light-blaster/flashing-lights.gif)

# Chicken Rain

Let's get started with coding in Minecraft! Why not add some life to your world? Maybe a chicken... No, let's have **LOTS OF CHICKENS**!!!
```

### Activities

Tutorials with **activities** enabled in the metadata have multiple _activities_, each consisting of several steps. An activity begins with a _level 2_ heading (``##``) followed by the activity name. The activity name is displayed in the tutorial control bar next to the step progress counter and step advance controls. An activity can have any number of steps, but no activity-specific text.

```markdown
## Activity 1

### Step 1

Instructions for step 1 of activity 1 here...

### Step 2

Instructions for step 2 of activity 1 here...

## Activity 2

### Step 1

Instructions for step 1 of activity 2 here...
```

### Steps

A step is where the user views and interacts with the instructions and hints for a tutorial action. The runner builds interactions from each _step_ section.

#### Default Syntax

By default, a step begins with a _level 2_ heading (``##``), followed by the step name.

#### Activity Syntax

If the tutorial has **activities** enabled in the metadata, steps begin with a _level 3_ heading (``###``), followed by the name.

#### Step format

The step can have any name, but it's common to use the _Step 1, Step 2,...Step n_ sequence for each heading.

```markdown
## Step 1

Instructions for step 1 here...

## Step 2

Instructions for step 2 here...
```

The text in the heading is shown only when the tutorial is viewed as a help page. It's ok to have additional text in the heading. The word 'Step' can even be left out since the tutorial runner will build the list of steps only from the content under the heading tag, ``##``. These are valid headings:

```markdown
### Step 3: Make a new variable
```

>--or--

```markdown
## Make the sky rain chickens
```

The editor automatically parses the markdown and populates the user interface from each step section.

### Hints

Hints provide additional information and code suggestions to help the user complete the step.

#### Default Syntax

In each step, any text before the first code snippet or image is automatically displayed to the user in the tutorial caption. The remaining text, block examples, etc. are displayed in the ``hint`` dialog when the user clicks the caption or hint button.

#### Explicit Syntax

If the **explicitHints** flag is specified in the tutorial metadata, the tutorial will only show hints that are explicitly defined with the hint tag, as follows: `#### ~ tutorialhint`. The hint automatically terminates at the next heading. One hint can be specified per step, and if no hint is specified all text (including blocks) will be displayed in the tutorial caption.

````markdown
#### ~ tutorialhint
Put in an 'on chat' command and rename it to chicken.

```blocks
player.onChat("chicken", function () {
})
```
````

### ~ hint

#### Simple, short descriptions

During an interaction, the step description (all text before the first code block or image) is shown in the caption. If the paragraph length goes beyond the display length of caption, a "More" button appears in order to view the rest of the paragraph. It's best to keep the paragraph short enough to so all of it appears in the caption without requiring the user to click to see it all. If your instructions need more text, you can just create an additional step to split up the activity.

### ~

### Images

Using images in steps is a simple and powerful way to reinforce concepts and convey ideas. Images can be included as part of step descriptions. You specify an image using the standard markdown format.

```markdown
![Agent building a tower](/static/tutorials/agent-tower.png)
```

A step with and image might have text like this:

```markdown
## Introduction @unplugged

Have the agent build a tower! Make a command to tell it how many levels to build.

![Agent building a tower](/static/tutorials/agent-tower.png)
```

Images appear in steps that have either the [fullscreen](#fullscreen) or [unplugged](#unplugged) modifiers present, or when a step hint is viewed.

Images should be hosted under the ``./docs/static/`` folder path of the editor project's repository files. The relative URL in markdown begins with just ``/static/`` though.

Image formats typically used are PNG, JPEG, and GIF.

### ~ alert

#### Image size considerations

It's important to consider that image size can affect the load time and therefore
impact the experience of the user during a tutorial. Also, images that are too large can consume the viewing area where the tutorial is displayed. Try to economize tutorial images both in file size and dimensionally.
Recommendations for images are:

* **File size**: 1 MB or less
* **Dimensions**: 800 pixels wide or less

### ~

## Step modifiers

To add a special behavior to a step, use a step modifier:

### fullscreen

If you want to include a dramatic introduction or make certain that a special message is seen, you can use the ``@fullscreen`` tag. The section is displayed in an overlay window on top of the tutorial screen and isn't shown in the caption as part of the tutorial flow. You include it in your tutorial like this:

```markdown
# Chicken Rain

## It's time to code! @fullscreen

Let's get started with coding in Minecraft! Why not add some life to your world? Maybe a chicken... No, let's have **LOTS OF CHICKENS**!!!

![Chicken Rain](/static/tutorials/chicken-rain.gif)

## Step 1: Make a new variable

...
```

### unplugged

If you want to display your tutorial step in a dialog and then have it skip to the next step automatically, use ``@unplugged``. This feature is typically used for introductory steps.

```markdown
# Chicken Rain

## It's time to code! @unplugged

```


### tutorialCompleted

To signify that this step in the tutorial is the "last step", even if more steps are present in the markdown, use ``@tutorialCompleted``. This has no impact on how tutorial progress is displayed; it is only used by MakeCode editors that do something external when a tutorial is completed.

```markdown
# Chicken Rain

## This is the last step @tutorialCompleted

## This is a bonus activity that comes after the last step

```

## Using blocks

### Hint blocks

If you include blocks in a step, they are shown when the user displays the hint for the step.
The blocks are specified the same as in any other markdown document. During the step interaction, only the blocks inside the ```` ```blocks```` section are available in the categories (drawers) of the Toolbox.

````
## Step 3 - Spawn Chicken

Put in ``||mobs:spawn||`` to spawn a chicken at your position.  
The code under ``||player:on chat command||`` will run when you type **chicken** in the Minecraft chat. **~0 ~0 ~0** is the relative 3D position of the player.

```blocks
player.onChat("chicken", function () {
    mobs.spawn(CHICKEN, pos(0, 0, 0))
})
```
````

### Ghost blocks

If you want extra blocks to appear in the Toolbox drawers during a step, then you add a ghost blocks section. This informs the user that additional blocks beyond those that are shown in the hint are availble to form a solution.

````
## Step 3 - Spawn Chicken

Put in ``||mobs:spawn||`` to spawn a chicken at your position.  
The code under ``||player:on chat command||`` will run when you type **chicken** in the Minecraft chat. **~0 ~0 ~0** is the relative 3D position of the player.

```blocks
player.onChat("chicken", function () {
    mobs.spawn(CHICKEN, pos(0, 0, 0))
})
```

```ghost
player.teleport(pos(0, 0, 0))
```
````

### Templates

A template is a section of blocks that you want to have already on the workspace when the tutorial begins. The tutorial steps can then build on the initial program code given in the template.

````
```template
player.onChat("blockleft", function () {
    agent.move(SixDirection.Forward, 1)
    agent.turn(TurnDirection.Right)
    agent.place(SixDirection.Back)
})
```
````


### JRes

You can add a JRes file to the project if your tutorial relies on one being present in the user's project. This is usually necessary when creating a tutorial that references tilemaps (copy the contents of tilemap.g.jres into a snippet).

````
```jres
{
    "transparency16": {
        "data": "hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "tile1": {
        "data": "hwQQABAAAACIiIiIiIiIiIiIiIiIiIiIiISIiIiIiIiISIiIiIhIiIiIhIiIiISIiIhIiIhIiIiIiIiEiISIiIiIiEhIiIiIiIiIiISIiIiIiIhISIiIiIiIiISIhIiIiIhIiIhIiIiIiISIiIiEiIhIiIiIiEiIiIiIiIiIiISIiIiIiIiIiA==",
        "mimeType": "image/x-mkcd-f4",
        "tilemapTile": true
    },
    "level": {
        "id": "level",
        "mimeType": "application/mkcd-tilemap",
        "data": "MTAxMDAwMTAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMjAyMDIwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMjAyMDIwMjAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAyMDIwMjAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMA==",
        "tileset": [
            "myTiles.transparency16",
            "myTiles.tile1",
            "sprites.castle.tileGrass2"
        ]
    },
    "*": {
        "mimeType": "image/x-mkcd-f4",
        "dataEncoding": "base64",
        "namespace": "myTiles"
    }
}
```
````

## Using Python

If the target supports Python, snippets can be written in JavaScript or Python directly.

## Python snippets

Using ``python`` after the triple tick like this:

````
```python
for i in range(100):
    mobs.spawn(CHICKEN, pos(0, 10, 0))
```
````

## Spy snippets (JavaScript to Python)

Snippets can also be written in JavaScript and automatically converted to Python
at display time. Use the ``spy`` section:

````
```spy
player.teleport(pos(0, 0, 0))
```
````

## Other languages

Note that if the target supports python, then snippets are written in the usual way like:

````
```typescript
mobs.spawn(CHICKEN, pos(0, 10, 0))
```
or
```blocks
mobs.spawn(CHICKEN, pos(0, 10, 0))
```
````

Users will have the option of clicking the Python icon to see the snippet in Python just like they can with Blocks and Javascript/Typescript.

## Adding tutorials to the home screen

To have a tutorial appear on the home screen, you will need to create or use an existing gallery and add a tutorial entry to it. See the
[home screen](/targets/home-screen#galleries) page for information about creating and adding to home screen galleries.

### JavaScript and Python tutorial ("Spy tutorials")

If you are able to author your tutorial in a language agnostic way,
you will be able to have a single source document for both JavaScript and Python. You can specify a single tutorial for multiple languages using the [otherActions](/targets/home-screen#otheractions) field in the tutorial code card.

### In-Context Tutorials
In context tutorials are tutorials that are loaded into an existing project, rather than into a blank one. The format is the same as for all tutorials. If you are writing a third-party tutorial, please see the [User Tutorials](/writing-docs/user-tutorials) documentation for information on how to share your content as an in-context tutorial.

For editor maintainers:
* Add ``recipes: true`` in the ``appTheme`` section of your [``pxtarget.json``](/targets/pxtarget#apptheme-apptheme) to enable in-context tutorials
* Optionally add a ``/docs/recipes.md`` file that contains a list of code cards referencing your in-context tutorials.

In order to select the proper language (blocks vs JavaScript vs Python), you should add
a ``"editor": "js"`` entry for JavaScript tutorials and ``"editor": "py"`` entry for Python tutorials to each code card.

## Testing

If you are writing a third-party tutorial, please see the [User Tutorials](/writing-docs/user-tutorials) documentation for information on how to preview and share your tutorials.

When developing your new tutorials, it is easiest to first render and view them as a markdown documentation page until all steps look OK to you. Going through all the steps several times using the tutorial runner might become quite tedious while developing the tutorial.

If you are running the local server, go to ``http://localhost:3232/tutorials`` to render the ``/docs/tutorials.md`` gallery page.

The [pxt checkdocs](/cli/checkdocs) command will compile all the tutorial snippets automatically.

```
pxt checkdocs
```

## Example

The following sample shows a simple 2 step tutorial.

````markdown
# Getting started

## Introduction @unplugged

Let's get started!

## Step 1 @fullscreen

Welcome! Place the ``||basic:show string||`` block in the ``||basic:on start||`` slot to scroll your name.

```blocks
basic.showString("Micro!")
```

## Step 2

Click ``|Download|`` to transfer your code in your @boardname@!

````

## Translations

Tutorials are translated via [Crowdin](/translate) like any other documentation page.

## Dependencies

If your tutorial requires the use of an extension, you can add them using the [package macro](https://makecode.com/writing-docs/macros#dependencies).
