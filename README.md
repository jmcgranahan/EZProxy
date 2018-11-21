# EZProxy
EZProxy is a software from OCLC, https://help.oclc.org/Library_Management/Ezproxy
One of the main keys is adding the correct database stanze. This repository will centralize the database stanzas and will be pulled to the EZProxy server nightly (unless there is a need for an immediate pull, which can be done via INFORM).
##
Guide to modifying the databases.txt file

* T = Title
* U = Base URL (https://help.oclc.org/Library_Management/EZproxy/Configure_resources/URL_version_1) - you do not need the full URL here; just the http://xxx.yyyy.zzz/ portion
** I would recommend that even if a site is https to use the http version here - people like to bookmark and websites tend to have old links on them
* HJ = HostJavaScript (https://help.oclc.org/Library_Management/EZproxy/Configure_resources/HostJavaScript_HJ) - I would recommend always using this, even if OCLC says to use "Host". If you use Host (https://help.oclc.org/Library_Management/EZproxy/Configure_resources/Host_H), please note that if there are any JavaScripts on those sites, they will not be correctly processed.
** I would recommend here to use the https version of the U above
* DJ = DomainJavaScript (https://help.oclc.org/Library_Management/EZproxy/Configure_resources/DomainJavaScript_DJ) - this is just the domain of the U line

Example:
T ProQuest (databases.txt)
U http://www.proquest.com/
HJ https://www.proquest.com/
HJ search.proquest.com
HJ https://search.proquest.com/
DJ proquest.com

* Notice in the ProQuest example, there are 3 HJ's. The first one is just the https version of the U line. That should always be present since more and more sites are going with https. The 2nd & 3rd HJ lines are also from proquest - just a different subdomain. With HJ, if you are listing a http site, you do not need to enter "http://" - it knows that already. The 3rd HJ is just the https version of the 2nd line. And then the DJ line captures all of the above since they are from the same domain.
* Also notice the "(databases.txt)" - this is added to every entry so that we can easily troubleshoot/locate entries if needed. In the EZProxy Admin interface, all of the database entries are lumped together in one big list so having this identifier (which this is the only place it appears) helps.

* Please keep the stanzas in alphabetical order by Title
* Please add the standard URL in the U, followed by the https version in the HJ line; for all others, HJ standard.url.com; then HJ https://standard.url.com.
* Please put the URLs in alphabetical order. Example:

T AACC (database.txt)
U http://www.aaccjnls.org/
HJ https://www.aaccjnls.org/
HJ aaccjnls.org
HJ https://aaccjnls.org/
HJ clinchem.aaccjnls.org
HJ https://clinchem.aaccjnls.org/
HJ jalm.aaccjnls.org
HJ https://jalm.aaccjnls.org/
DJ aaccjnls.org

At the top of databases.txt is a Trial Database section. Please add any trial databases here, marked with "(databases.txt, TRIAL)". It might be beneficial to you to add the date when added. 
