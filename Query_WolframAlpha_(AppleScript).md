Queries [WolframAlpha](https://www.wolframalpha.com/) for the text in
Pane 1 and returns a (somewhat complicated) description of the result.
You can press Enter again to view it as large type, assuming that's your
default action for text.

Note that the AppleScript depends on a PHP script that does the actual
communication with WolframAlpha. You'll need to put that script
somewhere in your PATH, or put it somewhere and write the entire path
into the AppleScript.

You'll also need a (free) [WolframAlpha
API](http://products.wolframalpha.com/api/) key, which you'll paste into
the PHP script below.

### Query WolframAlpha.scpt

``` applescript
using terms from application "Quicksilver"
    on get direct types
        return {"NSStringPboardType", "QSFormulaType"}
    end get direct types
    on process text query
        show large type (do shell script "alpha.php" & space & (quoted form of query))
    end process text
end using terms from
```

### alpha.php

``` php
#!/usr/bin/env php
<?php
    $query = urlencode(implode(" ",array_slice($GLOBALS['argv'],1)));
    $url = "http://api.wolframalpha.com/v2/query?input=$query&appid=<INSERT A WOLFRAMALPHA API KEY HERE>&format=plaintext";
    $results = simplexml_load_file($url);
    if ($results["success"] != 'true') {
        echo "Wolfram|Alpha got an error: ".$results->asXML();
        exit(1);
    }
    foreach($results->pod as $eachPod) {
        $textEls = $eachPod->xpath('.//plaintext');
        if (strlen(implode($textEls)) != 0) {
            echo $eachPod["title"].":\n\t";
            echo implode("\n\t",
                array_map(
                    function($textEl) {return str_replace("\n","\n\t",$textEl);},
                    $textEls));
            echo "\n\n";
        }
    }
    if (isset($results->assumptions)) {
        echo "ASSUMPTIONS:\n";
        foreach($results->assumptions[0]->assumption as $eachAssumption) {
            echo "\t".$eachAssumption["type"] ."\t".$eachAssumption["word"]."\n";
            foreach ($eachAssumption->value as $eachValue) {
                echo "\t\t".$eachValue["desc"]."\n";
            }
        }
    }
?>
```