Recursively searches through directories

-q Hide progress bars and banners
-x extentions (separated by a space e.g. `-x sh cgi log html php http zip txt`)
-C filter status codes e.g 403 to ignore Forbidden
-o Output file e.g. -o feroxInitial
-w wordlist
-u url

`feroxbuster -u http://10.10.123.1 -x txt php -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -C 403 -o feroxscan`
