# Intro
This tool is used to generate the report for [OSED](https://www.offensive-security.com/exp301-osed/) exam.

This is a modified version of [OSCP-Exam-Report-Template-Markdown](https://github.com/noraj/OSCP-Exam-Report-Template-Markdown) to suit OSED exam requirements.

# Installation
## Requirements

- [Pandoc](https://pandoc.org/installing.html)
- LaTeX (eg. [TeX Live](http://www.tug.org/texlive/)) in order to get `pdflatex` or `xelatex`
- [Eisvogel Pandoc LaTeX PDF Template](https://github.com/Wandmalfarbe/pandoc-latex-template#installation)
- [p7zip](http://p7zip.sourceforge.net/) (if you want to use the script, for generating the archive)

- ArchLinux 

```
pacman -S texlive-most pandoc p7zip
```

- openSUSE 

```
zypper in texlive-scheme-medium pandoc p7zip-full
```

- Ubuntu: 

```
sudo apt-get install pandoc texlive-fonts-extra texlive-latex-extra texlive-latex-recommended texlive-latex-base p7zip-full
```

## Downloading `eisvogel`

```
sudo wget https://raw.githubusercontent.com/Wandmalfarbe/pandoc-latex-template/master/eisvogel.tex -O /usr/share/pandoc/data/templates/eisvogel.latex`
```

## How to use

First, set your OSID in `generate.py`.

Then, write your report in `src/OSED.md` and your assignments in `assignments/assignment*.py`.

Once done, generate your report with:

```
$ ./generate.py
Generating the report...
Generating archive...
```

The report and the archive have been generated:

```
$ ls output
OSED-OS-XXXXX-Exam-Report.7z  OSED-OS-XXXXX-Exam-Report.pdf
```

To preview the generated PDF open `OSED-OS-XXXXX-Exam-Report.pdf`.

`OSED-OS-XXXXX-Exam-Report.7z` archive will contain the PDF along with the assignment files stored in `assignments/` directory.

```
$ ls
OSED-OS-XXXXX-Exam-Report.7z
$ 7z x OSED-OS-XXXXX-Exam-Report.7z
...
$ tree
.
├── assignment1.py
├── assignment2.py
├── assignment3.py
├── OSED-OS-XXXXX-Exam-Report.7z
└── OSED-OS-XXXXX-Exam-Report.pdf
```

What you need to submit to Offsec is only `OSED-OS-XXXXX-Exam-Report.7z`.
