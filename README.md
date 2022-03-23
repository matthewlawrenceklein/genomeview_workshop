## Hello and welcome guinea pigs/ lab friends!
### let us demo some genome view

#### a quick disclaimer: this is unfinished software! Things may be funky/broken/unintuitive. Thanks in advance for your time, patience, and infinitely helpful feedback.

## Let's get the genome view development branch!
From your local anvi'o codebase, run `git checkout genomeview-backend` to pull + sync the remote `genomeview-backend` branch. 

Genome View relies on an additional submodule called Fabric.js . We can make sure we have that by running
`git submodule update --init`

You should now be able to run `anvi-self-test --suite genome-view` without any hiccups. Open the resultant URL in Chrome, and lets go!

## Getting situated
![view](https://i.imgur.com/xsAfKnq.png)
The Genome View interface is comprised of three main areas
1. The 'main canvas' - this is where your visualization lives
2. The 'nav bar' - your one stop shop for quickly navigating
3. The 'settings pane' - an anvi'o classic! Easily accessible with the `s` shortcut

## Navigating the main canvas

Manually navigating the main canvas can happen in a few different ways. 
- Mousewheel up/down over the main canvas will zoom in/out
- Manipulating the nav bar (slide, condense, expand) will adjust the main canvas accordingly
- Supplying start/stop values for the input fields on the bottom left of the nav bar, followed by `enter`
- Clicking the `+` and `-` buttons on the bottom right of the nav bar will zoom in/out
- The main canvas also has a verticle scrollbar of its own to view obscured genome groups

## Learning about our genes

Genome View offers two main avenues for gene-level information
- The 'ephemeral tooltip', available by hovering over a gene arrow
- The 'deepdive tooltip', available by clicking on a gene arrow

Go ahead and mouse over any gene in the main canvas
- Is all the expected information rendered in the tooltip?
- Is the rendered data laid out sensibly?

Now, click on any gene to open the deepdive tooltip
- Is it immediately clear what additional information/UI is exposed here?
- Try blasting a gene - is this feature functioning as expected?

While we have the deepdive tooltip open, let's explore metadata
- Metadata is divided into two categories
    - tags - for short, keyword descriptors
    - descriptions - for longer, more thorough text associated with a given gene.
- Add a test metadata tag to a handful of arbitrary genes. I like to use 'cats' :)
- Your tags should immediately populate the metadata section of the tooltip
- You can query for tags against the entire sequence and instantly see your hits
    - In the metadata section, click "Query Sequence for Matches" for a given tag
    - Your visualization should:
        - zoom out to a depth containing all hits
        - glow each matched gene in the visualization for 5 seconds*
            - *the glow effect is _slightly_ broken right now ;)
- You can also query metadata from the settings pane. Speaking of...

## Exploring the settings pane

*At present, the settings pane contains a number of placeholder/in-production elements

Here's a brief overview of the various sub-sections in the settings pane, in order of appearance.
- __Genome Arrangement__ - where you can change the genome spacing (vertical height) value of each genome group, as well as arrange groups by user-supplied ordering methods. Gene-cluster functionality is a work in progress :)
- __Search__ - a versatile query tool
- __Genomes__ - mostly placeholder data here, although genomes can be clicked-and-dragged to rearrange them in the visualization
- __Group Layers__ - rearrange the constituent layers for each group. Show/hide layers, and recolor additional data layers
- __Scale__ - change values for the ruler layer in each genome group
- __Bookmarks__ - bookmarks are metadata at the sequence level. A bookmark saves the start/stop positions of your current zoom-level along with a title and description. Bookmarks will continue to be built out to persist additional session data. 
- __Gene Arrows/Links/Labels__ - all kinds of gene visualization stuff! too much to list!

## Try to do some things!
- Pick any gene and choose an annotation item to query - then try querying from the settings pane
- Did the above query zoom to a specific section of the sequence? Try saving a bookmark that reflects your search criteria.
- Change the "Color genes by" value from default to `COG_CATEGORY`
    - Check the "Link gene/label source" checkbox and select a new "Color genes by" value
    - Batch color gene-arrows by any criteria you'd like. Does this work as expected?
    - Reset function colors (bug* move the navbar to trigger a re-render)

## Some closing thoughts
- What worked as expected? what didn't?
- Was there any core functionality that you felt was lacking? missing entirely?
