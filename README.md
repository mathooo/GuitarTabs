# GuitarTabs
The tool translates tabs in syntax described below to a picture.

Usage: `python GuitarTabs.py`

### Tabs syntax

Tabs are displayed in a grid with fixed width. 

<div align="center">
  <img src="http://i.imgur.com/S0wQh7f.png"><br><br>
</div>

A line is devided into 4 selections, each of them containing up to 8 positions.

* tone - s/p (two integers)
	* s - number of string
	* b - number of bar
* multiple tones on a position - tone.tone. ... .tone
* next position in a selection - space
	* up to 8 tones in a selection
* next selection - newline
	* up to 4 selections
* next line - 2x newline

More formally:

```
string := integer [1, 6]
bar := integer [1, 20]
tone := string/bar
tones := tone.tones | tone
selection := tones selection | tones
line := selection \n line | selection
lines := line \n\n lines | line
```

For an example, see `example.txt` file.

> Dependencies can be installed:

> * sudo apt-get install librsvg2-bin imagemagick python-poppler-qt4
> * pip install svgwrite
