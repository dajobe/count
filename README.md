count : count fields in text files
==================================

This is a unix commandline filter handy for summarising quick greps in logs.

For example:
    grep stuff /path/to/apache/combined/log | count FIELD-NUMBER

such as wondering who is causing all the 404s?
    $ grep ' 404 ' /path/to/apache/combined.log | count 0
    Summary for field 0

    11.80.43.243   4  50.00%
    22.85.35.198   1  12.50%
    33.6.17.183    1  12.50%
    44.246.146.130 1  12.50%
    55.249.67.57   1  12.50%
    -------------- - -------
		   8 100.00%

and you can also get a quicker visual histogram:
    $ grep ' 404 ' /path/to/apache/combined.log | count --histogram 0
    Summary for field 0

    11.80.43.243   4  50.00% ##############################
    22.85.35.198   1  12.50% #######
    33.6.17.183    1  12.50% #######
    44.246.146.130 1  12.50% #######
    55.249.67.57   1  12.50% #######
    -------------- - -------
		   8 100.00% ############################################################


[Dave Beckett][http://www.dajobe.org/]
