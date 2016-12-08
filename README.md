#TrackMeNot
A security / privacy add-on Firefox edition

Track me not initiates searches based on rss feeds to supply key words. It can be used to generate some interesting "random" searches of the internet or "noise" in searches and web interaction to reduce quality of data stored by profilers.


TrackMeNot contains many hard coded variables. This extended version documents how to run a modified version and the changes you can make to include your own customisation.

Currently firefox add-ons are signed, so the aim would be to make all variables customise-able. Ultimately, it could be envisaged to include additional self modifying or self customisation to make an updated version called **Browser Bot**, which can be used to "intelligently search" / learn to oppose a Bot teacher, or research and BookMark relevant pages from a seed keywords file.

### Running a customised version of TrackMeNot

Back-up your settings folder, under .mozilla in GNU/Linux. Or run the developer edition of firefox in a VM.


#### Install the developer edition of Firefox, to run unsigned applications.

type about:config

scroll down to xpinstall.signatures.required 

change 'Value' from True to False

#### TrackMeNot

In firefox go to tools / add-ons and search and install TrackMeNot.  


### Running your own custom version

By making it easier to customise all variables is the first step to increasing the security of TrackMeNot. The initial audit shows too many variables are not customise-able thus making the bots actions more trackable.

Without changing the code a new user should update the default blacklist, the rss feeds are also important to generate web searches.

#### Updateable files

Find where the firefox extensions are stored. On Ubuntu 16.04 :

    .mozilla/firefox/20fzsdo8.dev-edition-default/extensions/


Install the source code for the TrackMeNot. Git clone the TrackMeNot directory.


note that the files are in the compressed directory

      trackmenot@mrl.nyu.edu.xpi


Clone the source code       
      
git clone https://github.com/wrapperband/TrackMeNot.git

The files can be edited and copied into the running system.


It is relatively easy to copy in an updated version of trackmenot.js . This file is in the root director so arc viewer can handle it.

Edit the file in the TrackMeNot, then copy it into the compressed .xpi file.

#### Editing trackmenot.js

The trackmenot.js contains a number of variables to tweak, the first is **var zeitgeist** an array of "influential" words (need audit) 

##### timeout

The next variable to adjust is timeout. Any common factor can indicate usage, a range is harder to eleiminate. When adjusting less important, or harder to monitor parameters consider that the change from norm could also be trackable. May be worth lengthening. 

var tmn_timeout = 6000;

##### burstTimeout

A low value parameter but common factor. Increased slightly.

var burstTimeout = 6000;


#### Editing options.html

The options.html is the next file which can be adjusted.

##### zeitgeist

Note : that it is sometime difficult to update a hierarchy of folders into a archived or compressed file. I had to back up the TrackMeNot archive file, delete the whole data directory, then import the new data directory including the updated option.html file. 

On line 157 of options.html you can see the modified time stamps from the  original edition. Again common patterns, in this case temporal repetition rates are easily identified and eliminated.

 <select id ="trackmenot-opt-timeout">
                                                        <option data-l10n-id="tmn.option.freq.10pm" id="t0" value="6000" > </option>
                                                        <option data-l10n-id="tmn.option.freq.5pm" id="t1" value="12000"  > </option>
                                                        <option data-l10n-id="tmn.option.freq.1pm" id="t2" value="60000"  > </option>
                                                        <option data-l10n-id="tmn.option.freq.30ph" id="t3" value="120000" > </option>
                                                        <option data-l10n-id="tmn.option.freq.10ph" id="t4" value="360000" > </option>
                                                        <option data-l10n-id="tmn.option.freq.1ph" id="t5" value="3600000"> </option>
</select>

Customise the repetition times, in the future the system could also vary these times to make it a less "track-able" feature. In the future simply adding or removing  a small random rmber will amke each person and session have different base timings. The noise will make it more difficult to identify. 

#### Adding none search links

As long as the text "trackmenot" is included in the description the link will be accepted as a search URL. The search terms will be included, which can be used to replace parts of identification codes.

Ideally the bot should follow links, which is envisaged for the Browser Bot version.


#### Customising Initiation Options  

trackmenot.js  
function initOptions() {
		enabled = true;
		tmn_timeout = 60034;
		burstMode = true;
		setSearchEngine();
		useTab = false;
		useBlackList = true;
		useDHSList = false;
		kwBlackList = ['satan', 'neo', 'acordians'];
		saveLogs = true;
		disableLogs = false;

Showing some slight modifications to initial values to customise personal versions. These should be automatically, or personally configurable,, the blacklist defaults and function requires further audit and consideration.

		
		
### TrackMeNot Audit : Comparison of Source Code with released version.  

#### Inconsistencies of Firefox version from Source code  

trackmenot.js 
Source code
Array.prototype.contains = function(obj) {
		var i = this.length;
		while (i--) {
			if (this[i] === obj) {
				return true;
			}
		}
return false;

Firefox release
	function containsObj(arr, obj) {
		var i = arr.length;
		while (i--) {
			if (arr[i] === obj) {
				return true;
			}
		}
		return false;



#### Trouble

Don't let the power get to your head and set click rates too high.

#### List of alternate rss feeds

https://ec.europa.eu/research/index.cfm?pg=rss

#### Anti Bot detection

Some movement of mouse is required on each page. Scroll down searches.

#### How and where are custom settings stored in TrackMeNot

The current settings are stored in a json file
    store.json

For Ubuntu directory is :

    .mozilla/firefox/jetpack/simple.storage/
    
 
 

Ref 1 : SimAttack: private web search under fire : https://jisajournal.springeropen.com/articles/10.1186/s13174-016-0044-x  

    Albin PetitEmail author, Thomas Cerqueus, Antoine Boutet, Sonia Ben Mokhtar, 
    David Coquil, Lionel Brunie and Harald Kosch

    


