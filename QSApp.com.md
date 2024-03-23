# QSApp.com

**QSApp.com** is the new home for Quicksilver on Mac OS X.

In the future, it will hopefully have a new sexy design, an up to date list of all the plugins available which will directly link into Quicksilver and a comprehensive wiki to help users.

### Helping With QSApp.com

If you're interested in helping get QSApp.com safely on the road to success, then there are several places where you can start.

* Help add content to this QSApp.com wiki. There is plenty of information already available in the [Quicksilver Google Groups](http://groups.google.com/group/blacktree-quicksilver) as well as the now dead [Blacktree](http://web.archive.org/web/\*/http://docs.blacktree.com/quicksilver) documentation site. Click on Quicksilver to the left of the linked Blacktree topic pages. A lot of the archives are dead ends, [Jun 30, 2007](http://web.archive.org/web/20070701170449/docs.blacktree.com/quicksilver/quicksilver?DokuWiki=48da35e168dfb532fdfc6d1a3d3172de) has a lot of info.
* Help launch the QSApp.com website, which would include:
  * Creating a new design and framework for the site to run on
  * Help update the [plugins system](http://qsapp.com/plugins)
* Help document the plugins available for Quicksilver by filling in this [Plugin Reference](Plugin\_Reference/)

### Volunteers

We’ve gotten a lot of offers to help with the web site. This is great to see.

The current web site is three basic parts.

1. The main page
2. The wiki
3. The plug-ins list

So here’s what we need volunteers for. If you plan to work on something, put your name and maybe a link to your user page on the wiki. Leave some way for people to contact you (but I wouldn’t just post your e-mail address here).

#### Wiki

For the Wiki, if anyone has experience creating themes for MediaWiki (or would like to try it out), it would be nice to have a cool custom theme that went along with the main page, whatever that ends up being. We would also welcome any contributions of content to the wiki.

Volunteers: [philostein](http://lovequicksilver.com)

#### Plug-ins

Now, for the more technical PHP nerds among us, the plug-in system. Patrick has put something together that generates a list of plug-ins for humans to look at. What we eventually need is something that Quicksilver can look at to install and update plug-ins like it used to. We haven’t had any luck getting the code from Alcor, but we might be able to reverse-engineer it.

1. Do some stuff with plug-ins in Quicksilver.
2. Go to the Console and search for “qs0.blacktree.com”
3. Take the URLs you see there and use `wget` or `curl` to pull down the contents

The results should be XML property lists. We need to figure out the structure and how the script responds to various activities in the app. We also need it to have a source of data. Based on the detail in the current output, I’m guessing it should be able to extract each plug-in’s zip file and examine the Info.plist to get details. It doesn’t make sense to do this in real-time on every request, so probably some sort of database or even a file to cache the details would be good.

Volunteers: Etienne, [Jay Williams](http://myd3.com/)

Anyone working on anything other than the wiki should probably know at least the basics of git.

***

If you're still stuck on things to do, then you can always email help@qsapp.com for a chat with Patrick, Rob and some of the other guys who've decided to help run the site (this could be you if you want!)
