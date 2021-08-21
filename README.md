<!-- insert
---
title: GoHugo Shorturl
date: 2021-08-21T16:25:33
gometa: "joly.pw/gohugo-shorturl git https://github.com/cljoly/gohugo-shorturl"
---
end_insert -->
<!-- remove -->
# GoHugo Shorturl
<!-- end_remove -->

## Install

If you haven’t used hugo modules before:
```
hugo mod init <my-module-path>
```
more details in [hugo docs](https://gohugo.io/hugo-modules/use-modules/).

```
hugo mod get -u -v joly.pw/gohugo-shorturl
```
and edit your hugo config, for instance for `config.toml`

``` toml
[module]
  [[module.imports]]
    path = "joly.pw/gohugo-shorturl"
```

## Use

Imagine we want to create the short url *https://my.site/a* and to have it redirect to *https://gohugo.io/content-management/archetypes/#directory-based-archetypes*:
```
hugo new --kind shorturl content/a.md
```
and then edit `content/a.md`:
``` yaml
---
title: "A"
date: 2021-03-07T13:57:13Z
draft: true
type: "shorturl"
shortto: ""
---
```
Change the `shortto` above to *https://gohugo.io/content-management/archetypes/#directory-based-archetypes* and `draft` to `false`
``` yaml
---
title: "A"
date: 2021-03-07T13:57:13Z
draft: true
type: "shorturl"
shortto: "https://gohugo.io/content-management/archetypes/#directory-based-archetypes"
---
```

Then deploy *my.site* and open *https://my.site/a*, you will be redirected!

## Other parameters

See https://developers.google.com/search/docs/advanced/robots/robots_meta_tag?hl=en#directives

## Contribute

You may use a local version of this module in hugo like this:

```toml
[module]
replacements = "joly.pw/gohugo-shorturl -> /some/path/gohugo-shorturl"
[[module.imports]]
path = "joly.pw/gohugo-shorturl"
```

Please consider sending a PR with your patches, it’s always appreciated and will save you the trouble of maintaining the changes on your own!
