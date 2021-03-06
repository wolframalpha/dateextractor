# dateextractor

Basic Example is given in the `DateFinder.py` file itself!

	from DateExtractor import DateFinder

	df = DateFinder()

    # This `find_dates(text)` returns a list of datetime objects taking a string/buffer as a parameter 
    date_list = df.find_dates('<foobar> (oct 2013 to december 2014) </foobar>')

    print date_list
    # prints:  [datetime.datetime(2013, 10, 1, 0, 0), datetime.datetime(2014, 12, 1, 0, 0)]
    
    print DateFinder.get_period(date_list[0], date_list[1], in_years=True)


## SOME TESTCASES

```
from DateExtractor import demo
demo()

| TEXT                                           | DATE                         |   DURATION(year) |
|------------------------------------------------+------------------------------+------------------|
| worked from 10 may 00 to present               | ['10-05-2000', '04-01-2017'] |            16.65 |
| 10/July                                        | ['01-07-2010']               |                  |
| July/99 to July/99                             | ['01-07-1999', '01-07-1999'] |             0    |
| 10/2016                                        | ['01-10-2016']               |                  |
| 10-July-00                                     | ['10-07-2000']               |                  |
| 10-July 00 - 1-June 02                         | ['10-07-2000', '01-06-2002'] |             1.89 |
| July-2017                                      | ['01-07-2017']               |                  |
| 10 July, 2000                                  | ['10-07-2000']               |                  |
| 10th July, 2000                                | ['10-07-2000']               |                  |
| July, 2000                                     | ['01-07-2000']               |                  |
| July 15                                        | ['01-07-2015']               |                  |
| 04 2000 02 2001                                | ['01-04-2000', '01-02-2001'] |             0.84 |
| April 2014                                     | ['01-04-2014']               |                  |
| Duration: May 2013 - June 2014                 | ['01-05-2013', '01-06-2014'] |             1.08 |
| Accenture(Oct 2012 - Present)                  | ['01-10-2012', '04-01-2017'] |             4.26 |
| Barclays 1/2/12 - 12/12/13                     | ['02-01-2012', '12-12-2013'] |             1.94 |
| Worked from June'14 to June'15                 | ['01-06-2014', '01-06-2015'] |             1    |
| June'13 - till date                            | ['01-06-2013', '04-01-2017'] |             3.59 |
| period Nov 2014 October 2016                   | ['01-11-2014', '01-10-2016'] |             1.92 |
| period : October 2012 Nov 2014                 | ['01-10-2012', '01-11-2014'] |             2.08 |
| worked duration may 2011  december 2012        | ['01-05-2011', '01-12-2012'] |             1.59 |
| may'12 - december'13                           | ['01-05-2012', '01-12-2013'] |             1.59 |
| december 12 may 17                             | ['01-12-2012', '01-05-2017'] |             4.41 |
| <foobar> (oct 2013 to december 2014) </foobar> | ['01-10-2013', '01-12-2014'] |             1.17 |

```