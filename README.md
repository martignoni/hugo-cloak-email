# hugo-cloak-email

[![Awesome](https://awesome.re/badge.svg)](https://github.com/budparr/awesome-hugo)

## About

This is not a standalone theme. It is a [Hugo](https://gohugo.io) theme component providing a shortcode: `cloakemail` to cloak any e-mail or other messaging (`xmpp`, `tg`, etc.) or phone (`sip`, `tel`, etc.) address from spamming bots.

## Usage

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
    {{< cloakemail "john.doe@example.com" >}}
    ```
    or
    ```go
    {{< cloakemail address="john.doe@example.com" >}}
    ```
4. You may specify a protocol, this way:
    ```go
    {{< cloakemail address="john.doe@example.com" protocol="xmpp" >}}
    ```
    or
    ```go
    {{< cloakemail address="+1 212 664-7665" protocol="tel" >}}
    ```
5. or a class, this way:
    ```go
    {{< cloakemail address="john.doe@example.com" class="vip" >}}
    ```
6. or a text to be display instead of the e-mail address, this way:
    ```go
    {{< cloakemail address="john.doe@example.com" display="Send us a mail!" >}}
    ```

All parameters can be combined.

### Credits

Copyright © 2019 onwards, Nicolas Martignoni nicolas@martignoni.net.

Thanks to [@mxmehl](https://github.com/mxmehl) for ideas and explanations about other protocols and script fingerprinting.

This theme component was possible because of the work done by [@danieka](https://github.com/danieka) in [this pull request](https://github.com/gohugoio/hugo/pull/3935).

