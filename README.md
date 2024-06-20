# quarto.report

`quarto.report` is a Quarto extension that facilitate the creation of well-designed PDF reports with Quarto. It's the heir of `pagedreport`, an [R package](https://pagedreport.rfortherestofus.com/) based on `pagedown` that was hard to maintain due to the initial design choices. `quarto.report` relies on CSS and [`weasyprint`](https://weasyprint.org/) to produced an high-quality output.

It contains three templates designed for prints. Elements like logo, colors, fonts or size can be customized through parameters in the YAML header.

> Since it's Quarto, your code chunks can be R, Python or Julia. Pick your best choice !

### Chalk

`chalk` is a dual-tone template with both an accent and a third color.

CHALK MOCKUP

### Typewriter

This report is heavily inspied by the [report sample](https://github.com/CourtBouillon/weasyprint-samples/raw/master/report/report.pdf) of Weasyprint. `typewriter` has a main image on first page and use a single accent color. Its best uses are for corporate reports but it can also be use in a parametrized context.

TYPEWRITER MOCKUP

### Corner

`corner` template has been designed to be used in a parametrieed context. It's well suited to produce hundreds of different reports.

CORNER MOCKUP

## How-to

### Quarto extension

First install the extension using `quarto`:

```
quarto use template kantiles/quarto.report
```

### `weasyprint`

Also install `weasyprint` (the back-end). You need to have Python installed first. Follow the instruction for your system [here](https://doc.courtbouillon.org/weasyprint/stable/first_steps.html#installation) :

- Windows : use the [executable](https://github.com/Kozea/WeasyPrint/releases) of the latest release
- MacOS: `brew install weasyprint``
- Linux: `apt install weasyprint`

### Choose your template

You can choose your template by changing the format in the YAML:

- Chalk template:

```
format:
    quarto.report-pdf+chalk
```

- Typewriter template:

```
format:
    quarto.report-pdf+typewriter
```

- Corner template:

```
format:
    quarto.report-pdf+corner
```

### Change the parameters

You can change the parameters either in your YAML header or in the `_quarto.yml` file at the root of your folder.
Not all parameters apply to all templates (`typewriter` has no third color as an example).

> Please note that the parameters all live under the `style` argument and be careful about the indentation.

```
style:
  font:
    header: "Outfit"
    main: "Montserrat"
    mono: "Fira Code"
    size: 12pt
  color:
    font: "#404040"
    font-accent: "#fdfdfd"
    accent: "#123456"
    third: "#987654"
  pagesize:
    width: 210mm
    height: 297mm
  logo: url(path_to_logo)
  main-img: url(path_to_img)
  ```

- `font` change the main font parameters like header font, main font or font for code (mono) or base size. You must have the fonts on your system or add a call to add them in an additional CSS file
- `color` change the mains colors. Either font color, or the color used when the background color is set on `accent` (`font-accent`)
- `pagesize` change the dimensions of the page. Can be use to setup the dimensions to landscape if needed.
- `logo` and `main-img` change the logo and the main background image (for `typewriter` only)

### Render

Render and enjoy the result !

## Programming languages

### Using R

### Using Python

## Examples in the wild

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

