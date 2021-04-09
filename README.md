Testing repository for [hugo-theme-sk3](https://github.com/J-Siu/hugo-theme-sk3) with RStudio + blogdown.

## Node

- 2020-04-09 `blogdown::build_site(build_rmd = TRUE)` with rmd files seems to work correctly only when blogdown is not running server(`blogdown::stop_server()`)

- 2020-04-09 Created testing website
  - https://blogdown-sk3-test.jsiu.dev/
  - With following color
    ```toml
    [Params.color]
    bg     = "black"
    border = "red"
    link   = "green"
    text   = "orange"
    ```
  - Use `blogdown::build_site()` to build `public` folder.
- 2020-04-09 As of blogdown 1.2, if using hugo youtube shortcode in `.rmd` file, must use format `{{% ... %}}`, not `{{< ... >}}`, though both are valid for `.md` file.
## Steps to recreate this manually in RStudio console

> Follow step 1-7 if you want to create this test manually.
> Jump to step 8 if you download/clone this repository directly.

1. `install.packages("blogdown")`
2. `blogdown::install_hugo()`
3. `blogdown::hugo_version()`
   - Should show `[1] ‘0.82.0’` or higher
4. `blogdown::new_site()`
   - Delete config.yaml if exist in \<project root\>
5. `blogdown::install_theme("J-Siu/hugo-theme-sk3")`
   - Copy \<project root\>/themes/hugo-theme-sk3/config.demo.toml to \<project root\>/config.toml
   - Update \<project root\>/config.toml "theme = sk3" to "theme = hugo-theme-sk3"
6. `blogdown::new_post("youtube")`
   - Add `{{< youtube buiLez6AMU8 >}}` to end of file
7. `blogdown::new_post("youtube rmd",ext="R=.rmd")`
   - Add following to end of file

      ```txt
      Shortcode format with `<`
      {{< youtube buiLez6AMU8 >}}
      Shortcode format with `%`
      {{% youtube buiLez6AMU8 %}}
      ```

8. `blogdown::serve_site()`

## RStudio Version

```
platform       x86_64-apple-darwin17.0
arch           x86_64
os             darwin17.0
system         x86_64, darwin17.0
status
major          4
minor          0.5
year           2021
month          03
day            31
svn rev        80133
language       R
version.string R version 4.0.5 (2021-03-31)
nickname       Shake and Throw
```