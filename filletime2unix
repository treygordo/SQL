# Active Directory uses 'filetime' (epoch 1-1-1601) for lastlogontimestamp and pwdlastset attributes, as opposed to unixtime.
# filetime is measured in 'ticks' (units of 100 nanoseconds) from epoch start.
# 116444736000000000 = 'ticks' from 1-1-1601 to unix epoch of 1-1-1970
# divide by 10000000 to convert ticks to seconds.
# MySQL Query to convert filtetime to unixtime and set date format.  

date_format(from_unixtime(((lastlogontimestamp / 10000000) - (116444736000000000 / 10000000))), '%Y-%m-%d') AS last_logon
date_format(from_unixtime(((pwdlastset / 10000000) - (116444736000000000 / 10000000))), '%Y-%m-%d') AS pwdlastset
