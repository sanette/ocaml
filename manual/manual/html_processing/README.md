# HTML post-processing

This directory contains material for processing the html of the manual
(from the `../htmlman` directory).

The new html is output in `./docs` (the manual) and `./api` (the api).

## manual and api

There are two different scripts, `process_manual.ml` and `process_api.ml`.
The first one deals with all the chapters of the manual,
while the latter deals with the api generated with `ocamldoc`.

## How to build

```
cd ..
make web
```

Or, much faster if you know that `htmlman` is already up-to-date:

```
cd ..
dune exec html_processing/process_manual.exe silent
dune exec html_processing/process_api.exe overwrite silent
dune exec html_processing/process_api.exe compiler overwrite silent
```

(The `silent` keyword is optional. Remove it to have debug information.)

## How to browse

From the `html_processing` directory:

`firefox api/index.html`

`firefox docs/index.html`
