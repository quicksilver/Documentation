This Applescript requires you to sign up on SuperTweet.net. Follow these
instructions to install the script:

-   Sign up on [SuperTweet.net](http://supertweet.net) and authorize it
    with your twitter account.
-   Copy and paste the script below into the Applescript Editor
    Application
-   Edit the 'MyUserName' and 'MyPassword' section of the script with
    your Twitter username and password
-   Save the Applescript to your Quicksilver actions folder, as explain
    on the main [Applescripts](Applescripts "wikilink") page

``` applescript
using terms from application "Quicksilver"
    on process text tweet
        set twitter_status to quoted form of ("status=" & tweet)
        set results to do shell script "curl --user MyUserName:MyPassword" & " --data-binary " & twitter_status & " http://api.supertweet.net/statuses/update.json"
        -- display dialog results
        return nothing
    end process text
end using terms from
```