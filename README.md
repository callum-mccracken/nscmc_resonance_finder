# ncsmc_resonance_finder

Python modules to help process eigenphase_shift files and find resonances

Main script is `resonance_finder.py`.

You feed it a filename (full path), and it'll do a few things:
- create a new file in the same directory as the first, with "_flipped" at the end.
  - This file has columns rearranged and phases flipped if needed.
  - (when I say flipped I mean "with no large jumps from numerical overflow, e.g. from 89 to -89")
- Then it'll read through each channel and look for resonances.
  - it'll tell you where each one is (e.g. "6-0 column 3")
  - type of resonances = "strong": >90 degrees, "possible": > 60 degrees
  - it'll make plots of strong resonances
    - (and save those in the `resonances` directory, created when script is run)
  


## Getting Started

`git clone` this, or if you're on Cedar you can find a clone in `exch`.

`git pull origin master` to get the latest version. 

You'll want to run `resonance_finder.py`. There are a couple ways to do this:

- run the file like `python resonance_finder.py -f <filename>`

- open the file and change the line where you set `filepath`, then run it

### Prerequisites

Python (3.7.4 ideally, other versions may work)

`numpy` is also needed.

On cedar or a local machine, use `pip install --user numpy`
