
[![fwatcher](http://i.imgur.com/vy4T9a6.png)](#)

# fwatcher

 [![Support me on Patreon][badge_patreon]][patreon] [![Buy me a book][badge_amazon]][amazon] [![PayPal][badge_paypal_donate]][paypal-donations] [![Version](https://img.shields.io/npm/v/fwatcher.svg)](https://www.npmjs.com/package/fwatcher) [![Downloads](https://img.shields.io/npm/dt/fwatcher.svg)](https://www.npmjs.com/package/fwatcher)

> Watch files for changes.

## :cloud: Installation

```sh
$ npm i --save fwatcher
```


## :clipboard: Example



```js
// Dependencies
var FileWatcher = require("fwatcher")
  , Logger = require("bug-killer")
  ;

// Listen for changes for 5 seconds
var watcher = FileWatcher(__dirname + "/test.txt", function (err, ev, path) {
    if (err) { return Logger.log(err, "error"); }
    Logger.log([ev, path].join(" "));
});
setTimeout(watcher.off.bind(watcher), 5000);


// Listen only for one change
FileWatcher(__dirname + "/once.txt", true, function (err, ev, path) {
    if (err) { return Logger.log(err, "error"); }
    Logger.log([ev, path].join(" "));
});
```

## :memo: Documentation


### `Watcher(path, handler)`
Creates a new instance of the internal `Watcher`.

#### Params
- **String** `path`: The path to the file.
- **Function** `handler`: A function called when the file changes.

### `off()`
Removes the listener.

### `FileWatcher(path, options, callback)`
Creates a new file watcher.

#### Params
- **String** `path`: The path to the file.
- **Boolean|Options** `options`: A boolean value representing the `once` value or an object containing the following fields:

 - `once` (Boolean): If `true`, the handler is deleted after first event.
- **Function** `callback`: This function will be called when the file is changed or renamed. The first parameter is the error, the second one is
the evenit name and the third one is the file path.

#### Return
- **Watcher** The watcher instance.



## :yum: How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].


## :sparkling_heart: Support my projects

I open-source almost everything I can, and I try to reply everyone needing help using these projects. Obviously,
this takes time. You can integrate and use these projects in your applications *for free*! You can even change the source code and redistribute (even resell it).

However, if you get some profit from this or just want to encourage me to continue creating stuff, there are few ways you can do it:

 - Starring and sharing the projects you like :rocket:
 - [![PayPal][badge_paypal]][paypal-donations]—You can make one-time donations via PayPal. I'll probably buy a ~~coffee~~ tea. :tea:
 - [![Support me on Patreon][badge_patreon]][patreon]—Set up a recurring monthly donation and you will get interesting news about what I'm doing (things that I don't share with everyone).
 - **Bitcoin**—You can send me bitcoins at this address (or scanning the code below): `1P9BRsmazNQcuyTxEqveUsnf5CERdq35V6`

    ![](https://i.imgur.com/z6OQI95.png)

Thanks! :heart:


## :dizzy: Where is this library used?
If you are using this library in one of your projects, add it in this list. :sparkles:


 - [`element-status`](https://github.com/callahanrts/element#readme) (by CallahanRTS)—An electron based status bar
 - [`rucksack`](https://github.com/IonicaBizau/rucksack-new#readme)—JavaScript and CSS bundler.
 - [`web-term`](https://github.com/IonicaBizau/web-term)—A full screen terminal in your browser.

## :scroll: License

[MIT][license] © [Ionică Bizău][website]

[badge_patreon]: http://ionicabizau.github.io/badges/patreon.svg
[badge_amazon]: http://ionicabizau.github.io/badges/amazon.svg
[badge_paypal]: http://ionicabizau.github.io/badges/paypal.svg
[badge_paypal_donate]: http://ionicabizau.github.io/badges/paypal_donate.svg
[patreon]: https://www.patreon.com/ionicabizau
[amazon]: http://amzn.eu/hRo9sIZ
[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RVXDDLKKLQRJW
[donate-now]: http://i.imgur.com/6cMbHOC.png

[license]: http://showalicense.com/?fullname=Ionic%C4%83%20Biz%C4%83u%20%3Cbizauionica%40gmail.com%3E%20(https%3A%2F%2Fionicabizau.net)&year=2015#license-mit
[website]: https://ionicabizau.net
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md
