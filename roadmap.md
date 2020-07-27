## Refactoring

- Use State monad for [Result] passing around?
    > Needs to have IO too. mtl?

## Features

- Parallel HTTP fetch for separate domains
- Better --only-failures output
- Cache length option should accept units: s, m, h, d - default to s
- More detailed HttpException errors
- Should be able to detect links without http:// or https:// prefixes
- Should detect if internet connection is down
- Should show line number of found links

## Bugs

- Can't parse links containing single quote marks
- Fetching message sometimes goes to more than one line, so next line doesn't replace it (saveCursor/restoreCursor?)
- Is an invalid URL an error?
    > Should an invalid URL count as an error? The parser shouldn't really pick up invalid URLs. But if it looks like one and fails then it is probably worth high-lighting.
- Edge case: shouldn't delay if only a single URL being checked

## In Progress


## Done

- Basic link parsing
- Basic link checking
- Should output file that problem occured in
- Should return correct exit code
- Should store recently tested links in .brokdb file
- Option for cache length
- Should space out requests
- Option for interval between requests
- Should be able to ignore specific URLs
    > List of URL prefixes
- --help command
- Use attoparsec
    > Already used by HTTP-conduit, so may as well use it
- Fixed InvalidURLException crash
- Fixed issue with HEAD request returning a 404
- Sees `https://` and `http://` as valid URLs
- Sees `https://*` as a valid URL
- Checks the same URL multiple times if in different files
