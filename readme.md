# ColdBox Elixir Rollup Integration

This extension brings [Rollup.js](http://rollupjs.org/) support to your ColdBox Elixir builds. 

## Install

First, ensure that you're using ColdBox Elixir v6 or newer. Next, install the extension like so:

```bash
npm install coldbox-elixir-rollup --save-dev
```

## Use

You're all set! Open your `gulpfile.js`, and add:

```js
elixir( function( mix ) {
  mix.rollup( "main.js" );
} );
```

This will, by default, compile `resources/assets/js/main.js` to `includes/js/main.js`. Should you require a non-standard base directory for your 
source files, begin the path with `./`. This instructs ColdBox Elixir to omit any default base directories.

```js
elixir( function( mix ) {
  mix.rollup( "./app/assets/js/main.js" );
} );
```

Similarly, if you require a different output directory, provide a file or directory path as the second argument to `mix.rollup`.

```js
elixir( function( mix ) {
  mix.rollup( "main.js", "public/build/bundle.js" );
} );
```

Now, you're specifying that you want to compile `resources/assets/js/main.js` to `public/build/bundle.js`.

If providing an array of source files, it might be useful to override the default base directory. If desired, specify a path as the third argument.


```js
elixir( function( mix ) {
  mix.rollup( [ "main.js", "other.js" ], null, "app/js" );
} );
```

With this adjustment, we'll compile `app/js/main.js` and `app/js/other.js`.

Lastly, should you need to override the default Rollup configuration, you may do so by either creating a `rollup.config.js` file in your project root, 
or by passing a Rollup config object as the fourth argument to `mix.rollup`. You can [learn more about Rollup config files here.](http://rollupjs.org/guide/#using-config-files)

## Contributions and Bugs

Project tracking for this project can be found at the [Ortus Solutions Jira](https://ortussolutions.atlassian.net/projects/ELIXIR/summary).  Please log all bugs, improvements, and features there.

Pull requests are welcome and encouraged.  Please [check on the Jira page](https://ortussolutions.atlassian.net/projects/ELIXIR/issues/?filter=allissues) before starting any large amount of work so your time isn't wasted.

Brad Wood (@bdw429s) has a [great guide on submitting pull requests.](https://www.ortussolutions.com/blog/submit-your-first-pull-request-to-an-open-source-project)  If you are unsure where to go, in need of help, or have a question, come ask in the #box-products channel on the [CFML Slack](http://cfml-slack.herokuapp.com/).
