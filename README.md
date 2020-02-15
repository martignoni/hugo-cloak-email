# hugo-cloak-email

[![Awesome](https://awesome.re/badge.svg)](https://github.com/budparr/awesome-hugo)

## About

This [Hugo](https://gohugo.io) theme component provides a shortcode.

## Features

Shortcode `cloakemail` cloakes e-mail or other messaging (`xmpp`, `tg`, etc.) or phone (`sip`, `tel`, etc.) addresses from spamming bots.

### Mandatory parameter

Address to cloak, e.g.
```go
{{< cloakemail "jane.doe@example.com" >}}
```
or via named `address` paramater:
```go
{{< cloakemail address="jane.doe@example.com" >}}
```
Don't indicate other URI parameters, for instance to indicate an e-mail subject. For such feature, use instead optional `query` parameter (see below).

### Optional parameters

- Use `protocol` to specify the protocol: `{{< cloakemail address="jane.doe@example.com" protocol="xmpp" >}}` or `{{< cloakemail address="+1 212 664-7665" protocol="tel" >}}`
- Use `display` to display any text on the page instead of the address: `{{< cloakemail address="jane.doe@example.com" display="Send us a mail!" >}}`
- Use `class` to indicate CSS classes to use: `{{< cloakemail address="jane.doe@example.com" class="vip company-a" >}}`
- Use `query` to specify a e-mail subject or other URI parameters (URI query): `{{< cloakemail address="jane.doe@example.com" query="subject=Message from contact form" >}}`. The query is never printed on the web page.

All parameters can be combined.

### How it works

Given address `jane.doe@example.com`, the shortcode

- Writes `<span class="cloaked-e-mail" data-user="eod.enaj" data-domain="moc.elpmaxe"></span>` in the web page.
- A CSS rule reverses the strings back to their original values and concatenates them with `@` in-between. No link is available yet.
- A Javascript builds then the link by creating a `<a href=...>` element.

## Installation

1. Add the `hugo-cloak-email` as a submodule to be able to get upstream changes later `git submodule add https://github.com/martignoni/hugo-cloak-email.git themes/hugo-cloak-email`
2. Add `hugo-cloak-email` as the left-most element of the `theme` list variable in your site's or theme's configuration file `config.yaml` or `config.toml`. Example, with `config.yaml`:
    ```yaml
    theme: ["hugo-cloak-email", "my-theme"]
    ```
    or, with `config.toml`,
    ```toml
    theme = ["hugo-cloak-email", "my-theme"]
    ```
3. In your site, use the shortcode, this way:
    ```go
    {{< cloakemail "jane.doe@example.com" >}}
    ```
    or
    ```go
    {{< cloakemail address="jane.doe@example.com" >}}
    ```
4. You may specify parameters (see above)

### Credits

Copyright © 2019 onwards, Nicolas Martignoni nicolas@martignoni.net.

Thanks to [@mxmehl](https://github.com/mxmehl) for ideas and explanations about other protocols and script fingerprinting.

This theme component was possible because of the work done by [@danieka](https://github.com/danieka) in [this pull request](https://github.com/gohugoio/hugo/pull/3935).
