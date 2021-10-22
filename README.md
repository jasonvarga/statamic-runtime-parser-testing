View the homepage and you'll see two dumps:
- One of the image field in the `home.antlers.html` template
- One in the `example.antlers.html` partial.

When using
- the regex parser, they're both `Asset` instances.
- the runtime parser, the one in the partial becomes a URL.

You'll also see an asset tag being used.

- On the home template, it works fine.
- The identical one in the partial throws an error.

If you want to inspect further, in the `src/Tags/Asset.php@index` method, `dump($this->params)`. You'll see that `url` is an array. It should be an `Asset`.

(Ignore the fact that we're trying to pass an asset object into a parameter called url. It's fine.)
