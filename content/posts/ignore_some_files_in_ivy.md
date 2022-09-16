+++
title = "ignore some files in ivy"
author = ["Wentao Ding"]
lastmod = 2022-09-17T00:30:07+08:00
tags = ["emacs", "tex", "myCode"]
categories = ["emacs"]
draft = false
+++

`latex` and `latexmk` generate some auxiliary files while compiling, which will be edited rarely. So it might be convenient to ignore them when switching buffers (`ivy-switch-buffer`) or finding files (`counsel-find-file`), which can be achieved by setting `ivy-ignore-buffers` and `counsel-find-file-ignore-regexp`, respectively.
<!--more-->
```emacs-lisp
(setq ivy-ignore-tex-aux-suffix '(".aux" ".bbl" ".fls" ".blg" ".nav" ".snm" ".fdb_latexmk" ".run.xml" "-blx.bib" ".toc" ".synctex.gz" ".out"))
(dolist (tex-aux-suffix ivy-ignore-tex-aux-suffix)
  (add-to-list 'ivy-ignore-buffers (concat "\\" tex-aux-suffix))
  (setq counsel-find-file-ignore-regexp (concat "\\(" tex-aux-suffix "$\\)\\|" counsel-find-file-ignore-regexp)))
```

We can excute the command `ivy-toggle-ignore` (`C-c C-a` by default) if we don't want to hide the ignored buffers or files temporarily.
