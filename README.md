#TrackMeNot
A basic add-on Firefox edition

TrackMeNot contains many hard coded variables. This extended version documents how to run a modified version and the changes you can make to include your own customisation.

Currently firefox add-ons are signed, so the aim would be to make all variables customiseable. Ultimately, it is envisage to include self modifing or self customisation in an updated version called **Browser Bot**, which can be used to "intelligently search" / learn or oppose Bot teacher, or research and BookMark relevant pages from a seed keywords file.

#### Running updated / your customised version of TrackMeNot

Back-up your settings folder, under .mozilla in GNU/Linux. Or run the developer edition of firefox in a VM.


Install the developer edition of Firefox, to run unsigned applications.

type about:config

scroll down to xpinstall.signatures.required 

change 'Value' from True to False

### Running your own custom version

By making it easier to customis all variables is the first step to increasing the security of TrackMeNot. The initial audit shows too many variables are not customiseable thus making the bots actions more trackable.

Without changing the code a new user should update the default blacklist, the rss feeds are also important to generate web searches.

#### Updateable files


.mozilla/firefox/20fzsdo8.dev-edition-default/extensions/

Git clone the TrackMeNot directory.

note that the files are in the compressed directory

trackmenot@mrl.nyu.edu.xpi

It is relatively easy to copy in an updated version of trackmenot.js . This file is in the root director so arc viewer can handle it.

Edit the file in the TrackMeNot, then copy it into the compressed .xpi file.

The trackmenot.js contains a number of variables to tweak, the first is **var zeitgeist** an array of "influential" words (need audit) 




#### Adding none search links

As long as trackmenot is included in the description the link will be accepted as a search URL. The search terms will be included, which can be used to replace parts of identification codes.
Ideally the bot should follow links, which is envisaged for the Browser Bot version.


#### Trouble

Don't let the power get to your head and set click rates too high.

