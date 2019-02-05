# hugo-cloak-email

## About

This is not a standalone theme. It is a [Hugo](https://gohugo.io) theme component providing a shortcode: `cloakemail` to cloak any e-mail address from spamming bots.

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

### Credits

This theme component was possible because of the work done by
[@danieka](https://github.com/danieka) in [this pull request](https://github.com/gohugoio/hugo/pull/3935).
