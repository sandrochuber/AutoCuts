# AutoCuts

## Build

1. Clone/Download repo
2. Install node: https://nodejs.org/en/. Enter command line and write 'node'. Executing 'process.versions' should give you a list of libraries and their used versions.
-  Run 'npm install -g node-gyp'. Needed to build c++-code.
-  Make sure Python is installed (Tested with Python 2.7.13 https://www.python.org/downloads/release/python-2713/).
3. Move into the local repo and run the 'install.bat' script. This downloads and installs all needed dependencies.
- cd into /src/addon
- Run 'node-gyp install 8.2.1' to get the correct node version.
- Run 'node-gyp configure --target=1.8.2 --arch=x64 --dist-url=https://atom.io/download/atom-shell'. This should result in a 'build' folder containing a VS solution 'binding.sln'.
- Open bindings.sln and ...
- switch to release configuration
- add openmp option
- add Preprocessor 'NOMINMAX'
- change additional include directory entry 'xxx\.node-gyp\iojs-1.8.2\include\node' to 'xxx\.node-gyp\8.2.1\include\node'
- build
- cd back to the root directory.
4. Run 'npm run electron-build' to build and run the app in production mode.
5. Run 'npm run electron' to just run the built app without rebuilding it.

## Create Windows installer
1. Run 'npm run pack-win32'.
2. RUn 'npm run installer-win32'.