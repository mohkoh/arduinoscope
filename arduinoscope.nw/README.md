## Node

This is the [node-webkit](https://github.com/rogerwang/node-webkit) version of Arduinoscope.

It's pretty basic, and just a proof-of-concept, for now.

## Binaries

Eventually, the main arduinoscope project will use this as the GUI, and binaries will be available for the 3 supported platforms.

## Building

For now, you will need to build it yourself, to get it running.

### Windows/Linux

You will need the [node-webkit](https://github.com/rogerwang/node-webkit) runtime for your platform, and the compiled version of serialport module. For everyonebut Macs, just download this project, and in the `arduinoscope.nw` directory, type `npm install`.

You will need to be able to compile node modules (so have `npm`, and `node-gyp` in your path.)

### Mac

On Mac, [node-webkit](https://github.com/rogerwang/node-webkit) is 32bit, only, so I had to do extra stuff:

    npm install
    cd node_modules/serialport
    nw-gyp configure --target=0.4.0
    sed -i bak s/x86_64/i386/g build/serialport.target.mk
    nw-gyp build

You will need to get a copy of `nw-gyp`, and put it in your path.

## Running

After the project is built, you can drag the `arduinoscope.nw` directory to the runtime, or run `nw arduinoscope.nw` in the command-line on Linux/Windows, if it's in your path.
