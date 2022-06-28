A pair of AppleScript actions wrapping PHP's `urlencode()/urldecode()`
functions, for quickly unescaping URLs (%20-\>space, %26-\>&, etc) in
query strings, or escaping a URL so you can paste it _into_ a query
string.

## Encode URL

``` applescript
using terms from application "Quicksilver"
    on process text theurl
        return do shell script "php -r 'echo urlencode(\"" & theurl & "\");'"
    end process text
end using terms from
```

## Decode URL

``` applescript
using terms from application "Quicksilver"
    on process text theurl
        return do shell script "php -r 'echo urldecode(\"" & theurl & "\");'"
    end process text
end using terms from
```