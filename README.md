# Pong
Pong is a remake of a classic game where two players fights to get the ball past the opposing players paddle.
You use the controller to control the paddle vertically, making sure the ball does not pass your paddle.
The game has a score limit, and the first player to get 11 points wins the game.

## Table of Contents

- [Precompiled](#precompiled)
- [Develop](#develop)
- [Compile and package](#compile-and-package)
- [Screenshots](#screenshots)
	- [Launcher](#launcher)
	- [Controller](#controller)

## Precompiled
The game packaged together with the controller.  
[All Releases](https://github.com/s111/gs-pong/releases)

Unzip and the ```pong``` folder can now be added to the game systems ```games``` directory.

## Develop
Download the repository:
```sh
git clone github.com/s111/gs-pong
```

Import the project into your IDE of choice. Choose a new maven project and import the pom.xml file. For your IDE to be able to compile the games, you first need to have maven generate the native libraries needed by the game. You do this by executing the following command:
```sh
mvn generate-resources
```
Then you need to set VM options to ```-Djava.library.path=target/natives```.

You should now be able to launch the game from your IDE. Remember that you need the game system running in the background for it to work.

## Compile and package
To package the game for distribuiton you must execute the following command:
```sh
mvn clean compile assembly:single
```

Now create this folder structure:  
```sh
pong/bin
```
Copy ```game.json```, ```screenshots.png``` and the ```controller``` folder into the ```pong``` folder. Copy the ```target/natives``` folder into it too and rename it to ```lib```. Now copy the jar file in the ```target``` folder into the ```pong/bin``` folder and rename it to ```pong.jar```.

You should now have a folder named ```pong``` which looks something like this:
```
pong/game.json
pong/controller/index.html
pong/controller/controller.js
pong/bin/pong.jar
pong/lib/lwjgl.dll
pong/lib/...
```
This folder can now be added to the game systems ```games``` directory.

## Screenshots

### Launcher
<img src="https://github.com/s111/gamesystem/blob/master/screenshots/pong.png" width="640">

### Controller
<img src="https://github.com/s111/gamesystem/blob/master/screenshots/pong_controller_select.png" width="320">
<img src="https://github.com/s111/gamesystem/blob/master/screenshots/pong_controller_play.png" width="320">
