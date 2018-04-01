About this fork
===============

This is a fork of [dcodeIO/bcrypt.js](https://github.com/dcodeIO/bcrypt.js) with node support stripped out, intended
only for running in the browser.

For projects using webpack, especially in projects created with react-scripts that have not been ejected, the reference
to node's crypto module results in webpack including mocks and polyfills intended to simulate a node environment in the
browser. This adds hundreds of kilobytes of unwanted modules to the bundle.

I created this fork to avoid ejecting my project.

Using the [original project by dcodeIO](https://github.com/dcodeIO/bcrypt.js) is strongly recommended. This fork may not
be maintained. If you have access to your webpack config, just disable the node environment completely.

Unit Tests
----------

If your unit tests run in node (as react-scripts tests do), the changes I've made will break them. In your tests you
will need to provide node's crypto module as the random fallback like so:

    import bcrypt from 'bcryptjs'
    import {randomBytes} from 'crypto'
    bcrypt.setRandomFallback(randomBytes)

Credits
-------
Forked from project by Daniel Wirtz at [dcodeIO/bcrypt.js](https://github.com/dcodeIO/bcrypt.js) (MIT-licensed).
Based on work started by Shane Girish at [bcrypt-nodejs](https://github.com/shaneGirish/bcrypt-nodejs) (MIT-licensed),
which is itself based on [javascript-bcrypt](http://code.google.com/p/javascript-bcrypt/) (New BSD-licensed).

License
-------
New-BSD / MIT ([see](https://github.com/dcodeIO/bcrypt.js/blob/master/LICENSE))
