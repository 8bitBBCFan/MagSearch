# MagSearch
With MagSearch one can search for an article within a magazine series such as MagPi, HackSpace, Elektor etc. by means of keywords.
MagSearch creates a database of keywords (>=2 chars) for each magazine series (magpi.db, hackspace.db) by scanning the textual content
of the PDF files. The creation of these databases is currently only possible on Linux systems. MagSearch was developed
for the Raspberry Pi system. See also the website https://magsearch.vanzon.nu.

By entering one or more keywords, the database is scanned for pages containing these keywords. MagSearch
detects whether pages in a magazine are sequential which most likely points to an interesting article and ranks
these articles based on the number of detected pages.

Quick use:
- Enter one or more keywords in the 'Search' field and press 'Enter' (or click the right mouse button).
  A result is displayed: Magazine number : page [occurrence on page], ... .
  Press control+B (or middle mouse button) to obtain the best page sequence per magazine (currently only 1 per magazine).
- The menu 'Help -> Manual' will give more information.

The database for MagPi contains currently 155 magazines and for HackSpace 81 magazines. New magazines can be added to
the database. The name of a magazine has a strict format such as 'MagPi' followed by a number (e.g. 'MagPi123', 'HackSpace52').
This format is specified in the configuration file 'config.yml'.

Installation requirements:
  - Python modules: PyPDF2, PyYaml, keyboard (this one should be installed as root with 'sudo pip3 install keyboard').
  - PDF viewer 'evince' has to be installed via 'Preferences -> Add/Remove Software - evince' or 'sudo apt-get install evince'.
  - Command line application 'pdftotext' (based on Poppler) via 'Preferences -> Add/Remove Software - pdftotext') or 'sudo apt-get
    install pdftotext'.
  - Create a directory '/home/pi/MagSearch' and copy the contents of the folder MagSearch in the .zip file into this directory.
  - Place downloaded magazines in the corresponding subfolder 'MagPi' or 'HackSpace'. This is necessary to be able to open a
    magazine at a specific page or to add a new magazine to the database. Check the paths in 'config.yml'.
    NOTE: the magazines are NOT part of this distribution and have to be downloaded by the user itself.
  - Open the command line in '/home/pi/MagSearch' and run 'python3 mag_gui.py' or ./mag_gui.py (possibly first 'chmod +x mag_gui.py').

Acknowledgements
Part of the English stopword list and the functions 'remove_stopwords' and 'freqdict' are taken from the website
'https://programminghistorian.org/en/lessons/counting-frequencies'. This website was the inspiration to continue this application.
