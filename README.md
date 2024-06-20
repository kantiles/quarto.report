# quarto.report

## What ?

A set of customizable templates for printed PDF in QUarto

MOCKUP

Child of pagedreport in R that was harder to maintain

## How to use it

- install extension
- install weasyprint
- change parameters (can be in a _quarto.yml file)
- render

## Examples in the live

use -> for a report
-> parametrised context

Example to IA2030 in partnership with R for the rest of Us

See some examples done in the past with R for the rest of Us + personal site
Call us for consulting work

## How to extend 

Get inspired, re-use, try it

Pay attention to the license please, please cite

## Why ?

Something lack in Quarto :

- we have Rmd + pagedown
- we have `typst`
- don't speak about Latex

but nothing for advanced layout for print, despite existing solutions like weasyprint, pagedjs or Prince

### Quarto

This solutions are supported by pandoc

CSS !

## How does that works ?

Pandoc template that pass variables to CSS.
In a way this is very near from the default implementation in Quarto (adding some CSS vars)

Plus three templates

Some hacks :
- no template partials
- prefer-html
- fig format to setup
- some tables tricks

## Roadmap

This is an experimental solution that aims at testing things. My hope is to get that integrated into Quarto

- see some issues about it in Quarto

