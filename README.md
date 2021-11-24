# log4brains-resolver-example

This repository demonstrates a bug in the [log4brains](https://github.com/thomvaill/log4brains) project.

## Description

In a multi-package project, when a default template is absent, as well as in the package directories,
the `--from` flag is ignored, and an error is thrown.

in this case in:
- `docs/`
- `packageone`
- `packagetwo`

## To reproduce:

Run:
```shell
npm run new:packageone
```

### Expected result

A new ADR is generated from the `templates/packageone.md` file

### Actual result

```
▶ npm run new:packageone         

> log4brains-resolver-example@1.0.0 new:packageone
> log4brains adr new --package packageone --from templates/packageone.md


? Title of the solved problem and its solution? foo
 ✖  The template.md file does not exist (docs/adr/template.md)
You can use this template (​https://raw.githubusercontent.com/thomvaill/log4brains/master/packages/init/assets/template.md​) as an example

 FATAL  The template.md file does not exist (docs/adr/template.md)
```
