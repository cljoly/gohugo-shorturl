# gohugo-shorturl

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
```
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
