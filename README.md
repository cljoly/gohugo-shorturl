<!-- insert
---
title: GoHugo Shorturl
date: 2021-08-21T16:25:33
gometa: "joly.pw/gohugo-shorturl git https://github.com/cljoly/gohugo-shorturl"
tags:
- Hugo
description: "🔗 Hugo module to create shorturls (so your shorturl like my.site/short can redirect to asitewithalong.name/andanevenlongerpath)"
---
{{< github_badge >}}
end_insert -->
<!-- remove -->
# GoHugo Shorturl
<!-- end_remove -->

![Min Hugo Version: 0.77.0](https://img.shields.io/badge/min%20Hugo%20version-0.78.0-lightgrey?logo=hugo)

Create shorter urls to external resources for your own convenience or to your own content, to get the [benefits described by Derek Sivers](https://sive.rs/su).

## Install

If you haven’t used hugo modules before (you need the go compiler):
```
hugo mod init <my-module-path>
```
more details in [hugo docs](https://gohugo.io/hugo-modules/use-modules/).

Then run:
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
