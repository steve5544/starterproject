# Ionic 2 + A-Frame Hello World app

You'll need a working Node environment with the latest Ionic version installed.

For setting up Node environments I recommend going with [nvm](https://github.com/creationix/nvm) and never use `sudo` to install your packages.
If you are using Ubuntu and want a guide for installing `nvm` and `node`, read this: [How to Install Node in Ubuntu](http://lobotuerto.com/blog/2013/02/19/como-instalar-node-js-en-ubuntu/) (it's in Spanish but you'll manage).

To install Ionic please refer to [this guide.](http://ionicframework.com/docs/v2/getting-started/installation/)


## How to run the app

First you need to clone the repo:

    git clone https://github.com/lobo-tuerto/a-frame-ionic2-hello-world.git


Then run:

    npm install


When that finishes, modify this file:
`a-frame-ionic2-hello-world/node_modules/@ionic/app-scripts/config/copy.config.js`


And add this at the end of the array:

    {
      src: 'node_modules/aframe/dist/aframe-v0.3.2.min.js',
      dest: '{{WWW}}/aframe/aframe.js'
    }


It should look something like this:

    // https://www.npmjs.com/package/fs-extra

    module.exports = {
      include: [
        {
          src: '{{SRC}}/assets/',
          dest: '{{WWW}}/assets/'
        },
        {
          src: '{{SRC}}/index.html',
          dest: '{{WWW}}/index.html'
        },
        {
          src: '{{SRC}}/manifest.json',
          dest: '{{WWW}}/manifest.json'
        },
        {
          src: '{{SRC}}/service-worker.js',
          dest: '{{WWW}}/service-worker.js'
        },
        {
          src: 'node_modules/ionic-angular/polyfills/polyfills.js',
          dest: '{{BUILD}}/polyfills.js'
        },
        {
          src: 'node_modules/ionicons/dist/fonts/',
          dest: '{{WWW}}/assets/fonts/'
        },
        {
          src: 'node_modules/aframe/dist/aframe-v0.3.2.min.js',
          dest: '{{WWW}}/aframe/aframe.js'
        }
      ]
    };


Finally, to see the app in the browser run:

    ionic serve


If you have the required files for Android deployment (I recommend USB debugging for easy testing on your phone):

    ionic run android


## Results

I was able to run the app in a Samsung Note 3 without problems.
There seems to be a couple of errors in the browser console, but didn't seem to affect the demo app.

If you do a more complex app with Ionic 2 + A-Frame, please do share your experience.


## Final notes

This was a very quick hack that demonstrates what steps you need to take to embed A-Frame into an Ionic 2 application.
If you want to see the specifics, then have a look at the commits (they are only a couple).

If you have comments on how to improve the integration I'll be glad to hear all about it.
