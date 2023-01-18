# MagSearch
With MagSearch one can search for an article within a magazine series such as MagPi, HackSpace, Elektor etc.
It creates a database of keywords for each magazine series (magpi.db, hackspace.db) by scanning the textual content
of the PDF files. The creation of these databases is currently only possible on Linux systems.
MagSearch was originally developed for the Raspberry Pi system.  

By entering one or more keywords, the database is scanned for pages containing these keywords. MagSearch
detects whether pages in a magazine are sequential which most likely points to an interesting article and ranks
these articles by the length of detected pages.

The database for MagPi contains currently 125 magazines and for HackSpace 62 magazines. New magazines can be added to
the database. The name of a magazine has a strict format such as 'MagPi' followed by a number (e.g. 'MagPi123', 'HackSpace52').
This format is specified in the configuration file 'config.yml'.

The result of a search displays the magazine and pages of occurrence and by clicking on the page the magazine is opened at the
corresponding page. In order to allow this:
  - the 'evince' PDF viewer has to be installed via Add/Remove Software
  - the magazines have to be present in specific subdirectories /home/pi/MagSearch/MagPi, /home/pi/MagSearch/HackSpace
    Note that the magazines are NOT part of this distribution but have to be downloaded by the user itself

