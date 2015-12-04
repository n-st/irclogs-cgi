irclogs-cgi
===========

A CGI script that uses [Pygments](http://pygments.org/) to colourise IRC logs
(in the format used by the ZNC log module), which are then served as a webpage.


The Apache config file included in this repo makes Apache
* serve ZNC's log directory,
* sort the lists of network and channel directories alphabetically,
* sort the list of logfiles per channel chronologically (newest first),
* and pipe all \*.log files through the included CGI script to colourise them.

The CGI script accepts any of "nojoins", "noparts", and "noquits" as a GET
parameter to hide all joins, parts, and quits (regardless of which parameter
was used).

Example URL (just a non-functional representation, of course):  
`https://example.com/irclogs/freenode/%23bash/2015-12-04.log?nojoins`


Installation
------------

* Copy/include `irclogs.apache.conf` into your Apache configuration and adapt
  the paths if necessary.
* Copy `irclog-colorizer` to the path you set in your Apache configuration.
* Make Apache reload its configuration and navigate to the appropriate URL.
  You should see a standard Apache directory listing, or a colourised version
  of an IRC log when you select one.
