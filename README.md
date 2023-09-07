# Use slides on Mac

brew install slides

use pandoc and basictex on Mac

brew install pandoc
brew install --cask basictex
sudo ln -s -v /Library/TeX/texbin/pdflatex /usr/local/bin/pdflatex
pandoc some.md -s -o some.pdf
