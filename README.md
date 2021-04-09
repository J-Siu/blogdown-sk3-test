## Steps in RStudio console

In new project console
1. `install.packages("blogdown")`
2. `blogdown::install_hugo()`
2. `blogdown::new_site()`
   - Delete config.yaml if exist at project root
3. `blogdown::install_theme("J-Siu/hugo-theme-sk3")`
   - Copy themes/hugo-theme-sk3/config.toml to project root
   - Update config.toml "theme = sk3" to "theme = hugo-theme-sk3"
4. `blogdown::new_post("youtube")`
   - Add `{{< youtube buiLez6AMU8 >}}` to end of file
5. `blogdown::serve_site()`