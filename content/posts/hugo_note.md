+++
title = "Hugo Note"
author = ["Wentao Ding"]
publishDate = 2022-10-03
lastmod = 2022-10-03T23:25:27+08:00
draft = false
+++

This is my note for writing blogs with `Hugo` and `Emacs`.

<!--more-->


## Cross Reference {#cross-reference}


### Link to Posts {#link-to-posts}

-   Create the link to other posts by [Hugo Note]({{&lt; ref "hugo_note.md" &gt;}}). See [Links and Cross References | Hugo](https://gohugo.io/content-management/cross-references/) and [titleref: Referencing Hugo posts by their titles ❚ A Scripter's Notes](https://scripter.co/titleref-referencing-hugo-posts-by-their-titles/) for more details.
-   When export markdown by `ox-hugo`, the backend will convert the angle to `&lt;` and `&gt;` by default. It provides a way to export the above link by
    ```:raw
    @@hugo:[description]({{< ref "" >}})@@
    ```

See [Shortcodes — ox-hugo - Org to Hugo exporter](https://ox-hugo.scripter.co/doc/shortcodes/#hugo-paired-shortcodes) for more details.


### Link to Equations {#link-to-equations}

It is the same as `LaTeX` by `mathjax`.


## Emacs Configuration {#emacs-configuration}

-   export: `ox-hugo` to export markdown file. Also, `org-hugo-auto-export-mode` exports markdown file once the org file being edited is saved, which is convenient if you want to check the effect frequently.
