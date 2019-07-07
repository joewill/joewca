---
title: "Ghost on Node on Bash on Ubuntu on Windows"
date: 2017-01-31
draft: false
---
This blog runs on [Ghost](https://ghost.org/). So far I'm really loving it. It's a blogging platform, pure and simple. Everything you need. Nothing you don't. Ghost is built on [Node.js](https://nodejs.org/en/).

I develop and write on a Windows machine. A [Surface Pro 4](https://www.microsoft.com/en-ca/surface/devices/surface-pro-4/overview) to be exact. Windows runs Node.js applications pretty well on it's own. But with the release of [Bash on Ubuntu on Windows](https://msdn.microsoft.com/en-us/commandline/wsl/about), I also have the ability to run Node.js from Linux (erm, on Windows).

Why would I do this? I've seen a lot of chatter lately about how cool Bash on Windows is. I have little experience with Linux. Being a primarily .Net developer. So I wanted to dip my toes in the water. Setting up my local copy of my Ghost blog seems like a good place to start.

The first thing I did was to install Bash on Ubuntu on Windows. The installation instructions can be found in the [installation guide](https://msdn.microsoft.com/en-us/commandline/wsl/install_guide).

Next I needed to install Node.js. I did some Google searching and landed on a great article by [David Gilbertson](https://twitter.com/D__Gilbertson) called [Running Node.js on Linux on Windows (with no VM)](https://hackernoon.com/running-nodejs-on-linux-on-windows-88bd12993bae#.52ycvg4ig).

In short I had to run the following command in my new Bash prompt:

`curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
sudo apt-get install -y nodejs`

That's all there is to it! So now we have Node.js installed. A quick `node -v` in Bash confirms it's installed correctly.

Now that Node.js is installed the next thing I wanted to do is see if I could start running Ghost. I pointed my shiny new Bash shell to the directory where my Ghost install lives and keyed in my usual command: `npm start'.

Unfortunately, this did not work. 

![Unsupported Node version](/content/images/2017/01/Bash_On_Windows_Ghost_Error.PNG)

The problem here is that I have the wrong version of Node.js. Thankfully there is a cool command line utility that can help solve the problem: [Node Version Manager](https://github.com/creationix/nvm). Or `nvm` for short. 

Ghost has a handy list of [Supported Node Versions](http://support.ghost.org/supported-node-versions/). So we can consult this list and use `nvm` to tell our new Linux on Windows environment which version we want to use. At the time of writing the latest version of Node.js supported by Ghost is 6.9. I can install and configure this version of Node.js using one simple command

`nvm install 6.9`

From there I did an `npm install` on the same directory as my Ghost installation. I wasn't sure if this was a needed step. I had installed using Windows before, but did not know if the packages were in the same place for the new Linux environment. I may do some more research here, but there is no harm in running the command again.

Afterwards I was met with another error. Fortunately like any good error message it provided steps to solve. One more command typed into bash `npm install sqlite3 --save` and the error was solved.

After all this I was able to use my usual command of `npm start` to fire up my local version of Ghost. I learned a bit about how to use Bash on Ubuntu on Windows. There are a couple of other tasks I may try out including getting git working. I'm stoked to put another tool in the toolbox.

Joe