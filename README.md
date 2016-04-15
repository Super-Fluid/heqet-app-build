# heqet-app-build
Builds of heqet-app and instructions for building it yourself. 
Don't clone; just download the files you want.

## Ready to go
### Mac
todo
### Linux
todo
### Windows
todo

## DIY
At the moment, neither Heqet nor HistoryGraph are on
hackage. So, you'll need to get their source as well as the source
of HeqetApp.

First, make sure you have `stack`: <http://docs.haskellstack.org/en/stable/README/>

Make a directory containing the `stack.yaml` file found here. Clone in the three repositories of code: `heqet`, `heqet-app`, and `history-graph`.

    mkdir heqet-app-build
    cd heqet-app-build
    cp .../path/to/stack.yaml .
    git clone https://github.com/Super-Fluid/heqet-app.git
    git clone https://github.com/Super-Fluid/heqet.git
    git clone https://github.com/Super-Fluid/history-graph.git
    
Now build it. This will take a few minutes.
    
    stack build
    
Now put the executable and the static files together. You can put them anywhere, but let's put them in a directory here called `build`.

    mkdir build
    cp -r heqet-app/static/ build/static
    
The exact path to the executable will depend on your machine. 

    cp heqet-app/.stack-work/dist/x86_64-osx/Cabal-1.22.5.0/build/heqet/heqet ./build/heqet
    
A bug is that you must be in the `build` directory to run the `heqet` executable and have it find the static files.

    cd build
    ./heqet
