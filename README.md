# chimneypot

[![npm version](https://badge.fury.io/js/chimneypot.svg)](https://badge.fury.io/js/chimneypot)

Chimneypot is a lightweight Node.js handler for GitHub webhooks. It allows you to listen to all kinds of GitHub events and execute functions on your server.

Featured in [Node Weekly Issue 122](http://nodeweekly.com/issues/122).

## Usage

Chimneypot was designed to be simple, succinct and easy to use.

To print to the console every time you receive a `push` event from your repo:

    var chimneypot = require('chimneypot');

    var pot = new chimneypot({
      port: 3000,
      path: '/hook',
      secret: '08394e1da557b56373ece704d5bcee45'
    });

    pot.route('push', function (event) {
      console.log('We have received a push event!');
    });

    pot.listen();

Chimneypot will then be listening for any push events to `*:3000/hook`. When it receives a `push` event, it will log to the console:

> We have received a push event!

## Installation

You can install [the Chimneypot npm package](https://www.npmjs.com/package/chimneypot) with the following command:

    $ npm install chimneypot --save

## License

Chimneypot is completely released into the public domain, using [The Unlicense](http://unlicense.org). To see the full license text included with the project, you can read the [LICENSE file](/LICENSE).
