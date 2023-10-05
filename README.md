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

First, clone this repo:

```bash

git clone https://github.org/FNNDSC/tslide-presentations
cd tslide-presentations
export REPO=$PWD
```

Next, choose a name for your presentation. Note that this name will also be used for the directory (folder) containing the presentation. I'd strongly recommend you don't use spaces in this name.

```bash
export PRESENTATION="dontusespaces"
```

Set the name of the base directory of your web server. This will probably vary on your Linux distro. Below is for arch Linux and friends.

```bash
# This is directory of your web server. For arch linux:
export HTMLDOCS=/srv/http/slides
```

Note the `cp` command below uses GNU flags. It will be different on macOS!

```bash
# Here is where you typically copy an existing presentation
# to create the basic structure of your next one. Obviously
# this is a one time deal. Don't do this next time otherwise
# you'll overwrite $PRESENTATION!
/bin/cp -prvdi tutorial_ChRIS-gettingStarted "$PRESENTATION"

export INPUTDIR=$REPO/"$PRESENTATION" 
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
./tsmake    --outputDir $OUTPUTDIR              \
            --inputDir $INPUTDIR                \
            --no-pageSplit                      \
            --slidesFile $INPUTFILE             \
            --slideListGlob "slide-*"           \
            --additionalDirList $INPUTDIR/figs  \
            --verbosity 3
```

# Now enjoy it

## system web server

If you have a web server (like `apache`) up and running, and if your `$OUTPUTDIR` is the correct dir for your web server, then you can point your browser to 

```html
localhost/slides
```

to see your slide presentation.

## or just python it 

Alternatively, you can use python to serve it on some port:

```bash
cd $OUTPUTDIR
python -m http.server 9100
```

And then find happiness at `http://localhost:9100`.

_-30-_
