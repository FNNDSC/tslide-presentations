# tslide-presentations
A repo to house/keep tslide presentations.

## What's this all about then?

These are text-based (although heavily `html` peppered) presentations that are meant to be processed by the `tsmake` engine to create presenation websites.

## Ok, how do I use?

Funny you asked. The steps are:

1. Setup some env variables -- really little more than the name of your presentation
2. Run `tsmake` appropriately
3. Fire up your browser
4. Marvel at the goodness.

## Ok, seriously. How do I use this?

Fine. Just make sure about dir permissions, your web server yada yada...

First, clone this repo and make a new dir for your presentation.

```bash
    git clone https://github.org/FNNDSC/tslide-presentations
    cd tslide-presentations
    export REPO=$PWD
    
    # This is directory of your web server. For arch linux:
    export HTMLDOCS=/srv/http/slides

    # This is the name of your presentation. Please please
    # please don't use spaces. Trust me. Also, this name
    # should also be the name of the directory within this
    # repo containing your presentation
    export PRESENTATION=somethingcool

    # Here is where you typically copy an existing presentation
    # to create the basic structure of your next one. Obviously
    # this is a one time deal. Don't do this next time otherwise
    # you'll overwrite $PRESENTATION!
    /bin/cp -prvdi tutorial_ChRIS-gettingStarted $PRESENTATION

    export INPUTDIR=$REPO/$PRESENTATION 
    export INPUTFILE=slides-all-master.hjson
    export OUTPUTDIR=$HTMLDOCS/$PRESENTATION

```

Now, build it. If you haven't got `tsmake` (it's in a repo called `tslide` -- go figure):

```bash
cd ~
cd src
git clone https://github.org/FNNDSC/tslide
```

Enter the repo dir, and run build your presentation:

```bash
    cd ~/src/tslide
    ./tsmake --outputDir $OUTPUTDIR             \
             --inputDir $INPUTDIR               \
             --slidesFile $INPUTFILE            \
             --slideListGlob "slide-*"          \
             --additionalDirList $INPUTDIR/figs \
             --verbosity 3
```

_-30-_
