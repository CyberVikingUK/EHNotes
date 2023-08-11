Used to see if there are shared areas or Anonymous access

`smbclient -N -L \\\\10.10.10.27\\` for initial scan
`smbclient -N  \\\\10.10.10.27\\<location>` to try and access something

You will see a smb: \> prompt, and you can use ls and get to retrieve files or even put if you need to place files there.

To log in as a specific user `smbclient \\10.10.10.27\\ -U <username>`

NOTE: DEPENDING ON THE VERSION OF SMBCLIENT YOU ARE USING, you may need to SPECIFY the use of S<B version 1 or SMB version 2. You can dp this with -m SMB2. Older versions of SMBclient (latest being 4.10 at the time of writing) use SMB1 by default.
