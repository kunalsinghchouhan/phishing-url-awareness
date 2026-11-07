# Test Results
Python version used: 3.12.0 | Operating system: Windows | Date: 8-11-2026
| # | Input                                   | Expected result         | Actual result                                             | Pass/Fail |
|---|-----------------------------------------|-------------------------|-----------------------------------------------------------|-----------|
| 1 | https://www.example.com/login           | No listed warning signs |No listed warning signs found. This does NOT prove safety. | Pass*     |
| 2 | http://192.0.2.10/account               | IP address + HTTP       |Uses an IP address instead of a familiar domain. Uses HTTP.| Pass*     |
| 3 | http://example.com@sample.invalid/login | @ symbol + HTTP         |Contains an @ symbol; inspect carefully. Uses HTTP.        | Pass*     |
| 4 | https://a.b.c.d.e.example.invalid/path  | Many hostname segments  |Contains many hostname segments/subdomains.                | Pass*     |
| 5 | https://xn--example.invalid/            | Punycode-style hostname |Contains a punycode-style hostname.                        | Pass*     |

## Notes

I learned how Python can inspect URL text and identify suspicious warning signs using conditions, regular expressions and URL parsing.
I was surprised that a URL can contain a familiar-looking domain before the @ symbol while the actual hostname is different.
The project also taught me that finding no warning signs does not guarantee that a URL is safe.