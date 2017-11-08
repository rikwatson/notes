# GitHub Gists

[GitHub](https://www.github.com) has a feature for having small 'snipets' of code (just a couple of files) which live outside the traditional [git](./git.md) repo's.

These 'gists' can be public (searchable) or private (only accessible by their own UUID)

A `gist` can be embedded inside a HTML (or [Markdown](./markdown.md)) via the following script (replacing the UUID with the `gist`'s UUID):

```html
<script src="https://gist.github.com/user-name/DEADBEEF.js"></script>
```

The raw text for the latest 'master' for a `gist` can similarly be accessed via:

```
https://gist.githubusercontent.com/user-name/DEADBEEF/raw
```

Use [defunkt/gist](https://github.com/defunkt/gist) for a command line interface.

# Example of to-do list:

- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item
