//Privacy Ghost//Last Updated//1230Z MARCH 14, 2025//  
//Introduction to OSINT//  
//**BLUF**: This walkthrough will cover the intelligence lifecycle, sock puppet accounts, collecting and compiling information, and putting that information into an organized report.//


# //OVERVIEW//

![](https://i.imgur.com/XeQe7lf.png)

## What is OSINT? (Open-Source Intelligence)

OSINT encompasses multiple methods for collecting, analyzing, and making decisions about data accessible in **publicly** available sources to be used in an intelligence context. The term **"open"** refers to overt, publicly available resources.
# //SECTION 1//

---
## Intro to OSINT

---
### The Intelligence Lifecycle

![The Intelligence Lifecycle](https://i.imgur.com/phNMCTr.png)

The [intelligence lifecycle](https://www.intelligence.gov/how-the-ic-works) is comprised of 5 steps (*or 6 depending on your source*):

1. Planning & Direction
	- Who is the target, why are you targeting them, when are you going to start collecting information on this target.
	- Basic Who, What, When, Where, Why is all identified in this phase.
2. Collection
	- Gathering information from publicly available data this can include; [MASINT](https://en.wikipedia.org/wiki/Measurement_and_signature_intelligence)/[SIGINT](https://en.wikipedia.org/wiki/Signals_intelligence)/[HUMINT](https://en.wikipedia.org/wiki/Human_intelligence_(intelligence_gathering))/[GEOINT](https://en.wikipedia.org/wiki/Geospatial_intelligence) that you can access. 
3. Processing & Exploitation
	- Interpreting that data you have collected, and how it can build your overall intelligence picture. *(Processing imagery, decoding messages, translating broadcasts, etc.)*
4. Analysis & Production
	- This is where you have evaluated all your data points that you have collected and produce "*finished intelligence*".
5. Dissemination
	- Finished intelligence is then delivered to whoever your recipient is. Finished intelligence can lead to requests for additional information, which triggers the cycle again.

---
### Sock Puppet Accounts

What is a Sock Puppet Account?

[Wikipedia](https://en.wikipedia.org/wiki/Sock_puppet_account) defines a Sock Puppet or a "Sock" as "*a false online identity used for deceptive purposes.*"  However, I would say that that definition isn't fully encompassing of what a Sock Puppet can be used for. They are a huge asset for privacy and [OPSEC](https://en.wikipedia.org/wiki/Operations_security) online for an investigator. Additionally it will protect the target if your investigation doesn't lead anywhere.

The point of wanting to use a sock puppet is to have no ties back to you while collecting information. You never want to let the person/organization know that you are collecting information on them.

#### Creating Effective Sock Puppets

You should not be creating Sock Puppets on **your IP**. You don't want these accounts to ever be tied back to you. If you are using a VPN keep the VPN in the area of where your Sock Puppet account actually "lives".

**Jake Creps** has a great blog on creating Sock Puppet accounts, unfortunately that site is no longer available, however I found an instance on the Way Back Machine which you can access and read his full article [here](https://web.archive.org/web/20200626065212/https://jakecreps.com/2018/11/02/sock-puppets/).

*If you want the key concepts you should take note of, see below:*

---

**THIS IS TAKEN DIRECTLY FROM HIS BLOG POST**

**The Setup**

Depending on who you ask, there’s an endless list of things you can do to remain anonymous while conducting investigations online.  You can go extreme and jump down the Michael Bazzell rabbit hole, or you can have a little less attention to detail and still do fine. If you’re interested in an almost full proof system, check his book [Hiding from the Internet](https://www.amazon.com/Hiding-Internet-Eliminating-Personal-Information/dp/1500397814). If you’re asking me how to create a successful sock puppet, I’m more of a subscriber of the [Pareto Principle](https://en.wikipedia.org/wiki/Pareto_principle); but I also don’t have much to lose if caught during an investigation like others may have (back to intent).  Here’s the 80/20 on what you need to get started.

1. A dedicated computer that is only used for investigations
2. Encrypted Email – Use [Proton Mail](https://proton.me/mail)
3. A burner phone number (expensive) or a Wi-Fi phone number (cheap or free)
4. A social media profile where your target is most active (choose option 1 or 2)
5. A couple different virtual machines
6. A blog or website (you can use a free blog like WordPress, Blogger, or Medium)
7. A VPN (you should probably have one anyway)

Now, this is just a start, but it will help you at least get started.  You will have to customize your avatar as you go along to maintain or add credibility.

---

Here is a great blog from garretmickey that **literally walks you through what they do to create the account**:

[ Sockpuppet Account Creation – My Process](https://garrettmickley.com/sockpuppet-account-creation/)

---

Lastly, see the [Sock Puppet Resources.md](Sock Puppet Resources.md2520Resources.md) for a list useful links for account set up.

---

🎉 **Congrats!** You are all done with the Sock Puppet Accounts! 🎉 You can close this section.

---
## Collecting Information

___
### How to Search for Information:
####  [[Search Engine Operators and Resources]]


`site:url.com`

╰➤ Returns results of just a specified website. *ex Halo 3 Red versus Blue site:roosterteeth.com*

`AND`

╰➤ Returns results with two specified inputs *ex. Halo 3 AND Red versus Blue site:roosterteeth.com.*

`OR`

╰➤ Returns results between two specified inputs *ex. Halo 3 OR Red versus Blue site:roosterteeth.com.*

`""`

╰➤ Returns results in order of the specified text *ex. "Halo 3 Red versus Blue" site:roosterteeth.com.

`*`

╰➤ Returns a wild card *ex. Halo 3 `*`  site:roosterteeth.com.*

`filetype:`

╰➤ pdf/xlsx/docx etc.  

`-`

╰➤ Used to remove a search input. *ex. site:roosterteeth.com -www*

`intext:`

╰➤ Used to search for specific text on a webpage. *ex. site:roosterteeth.com intext:Halo*

`inurl:`

╰➤ Used to search for specific text inside of a sites url. *ex. site:roosterteeth.com inurl:Halo*

`intitle:`

╰➤ Used to search for specific text in the title of a web page. *ex. site:roosterteeth.com intitle:Halo*

---
### Image OSINT:

---
#### Viewing EXIF Data

*What is EXIF data?*
**Exchangeable image file format** (`.JPG`, `.TIF`, `.WAV`, `.PNG`,`.WEBP`)

A lot of details can be found in metadata such as:
- Location data
- Type of device
- Date

Metadata can be extracted at this site:

╰➤ https://exifeditor.io -- Browser-based, fully private, free!

From a post on [reddit](https://www.reddit.com/r/photography/comments/1l0v0oz/what_are_the_best_exif_viewerseditors/):

- 100% browser-based, works instantly — no signup, no installation.

- Fully client-side: images never leave your browser (excellent privacy).

- Full EXIF editing support, with raw hexdump viewer for non-standard or corrupted EXIF data.

- Works great on mobile and desktop.

---
#### Physical Location OSINT

Looking into a target location via satellite data/google maps/street view to form a complete picture of any valuable information. 

This is mainly If you are going to be physically going to the location/on-site reconnoissance. 

**Things to look for:**
- Is there controlled private access to the location?
	- Protective measures like a single point of entry and exit
	- Guard shack/check-in locations where being required to show ID is needed 
- Is there anywhere you can park/stay that is covert/private.
- Entrances of Interest
	- Look for badge readers
	- Smoking areas
- Best roads to take/roads that are the most discrete. 
- [GeoGuessr](https://www.geoguessr.com/) is a resource for practicing breaking down and finding locations. 

A massive guide blog post can be found [here](https://somerandomstuff1.wordpress.com/2019/02/08/geoguessr-the-top-tips-tricks-and-techniques/) which is a huge helpful resource in geolocating based on a singular image.

---


### Email Address OSINT

---
#### Email Address Search Tools

There are **a lot** of ways to find email addresses here are just a few that you can use to start searching 👻

╰➤ https://Hunter.io/

╰➤ https://phonebook.cz/ 

╰➤ https://voilanorbert.com/

---
#### Email Verification 

Free tool to check if an email address actually exists. 

╰➤ https://tools.verifyemailaddress.io/

---
### Password OSINT

When looking for passwords via OSINT we are specifically looking for breached credentials.

**Dehashed**: a powerful data breech detection tool but, this tool is not **free**.

╰➤ https://www.dehashed.com/search#searchPricing

**Logoutify** (formerly breachdirectory)  unfortunately no longer a free tool :(

╰➤ [https://logoutify.com](https://logoutify.com/)

**Breach Parse**: a tool for parsing breached passwords. Includes download list.

╰➤ https://github.com/hmaverickadams/breach-parse



___




# Analyst Comments: 


Analyst: **Echo**  

*No LLMs were used in the creation of this document.*
# //END DOCUMENT// 

##  Sources, and Research:

https://en.wikipedia.org/

https://web.archive.org

https://www.intelligence.gov/

https://www.reddit.com

https://www.youtube.com/

#### Links:  

GeoGuessr:
	https://www.geoguessr.com/

GeoGuessr guide:
	https://somerandomstuff1.wordpress.com/2019/02/08/geoguessr-the-top-tips-tricks-and-techniques/

GEOINT:
	https://en.wikipedia.org/wiki/Geospatial_intelligence

Hiding from the Internet:
	https://www.amazon.com/Hiding-Internet-Eliminating-Personal-Information/dp/1500397814

HUMINT:
	https://en.wikipedia.org/wiki/Human_intelligence_(intelligence_gathering)

Hunter.io
	https://Hunter.io/

Intelligence life cycle:
	https://www.intelligence.gov/how-the-ic-works

Jake Creps Blog:
	https://web.archive.org/web/20200626065212/https://jakecreps.com/2018/11/02/sock-puppets/

MASINT:
	https://en.wikipedia.org/wiki/Measurement_and_signature_intelligence

OPSEC:
	https://en.wikipedia.org/wiki/Operations_security

Pareto Principle:
	https://en.wikipedia.org/wiki/Pareto_principle

Phonebook.cz
	https://phonebook.cz/ 

Proton Mail:
	https://proton.me/mail

Reddit Sock Puppet post:
	https://www.reddit.com/r/OSINT/comments/dp70jr/my_process_for_setting_up_anonymous_sockpuppet/

Reddit EXIF viewers post:
	https://www.reddit.com/r/photography/comments/1l0v0oz/what_are_the_best_exif_viewerseditors/

SIGINT:
	https://en.wikipedia.org/wiki/Signals_intelligence

Sock Puppets:
	https://en.wikipedia.org/wiki/Sock_puppet_account

The Cyber Mentor:
	https://www.youtube.com/watch?v=qwA6MmbeGNo

Voila Norbert
	https://voilanorbert.com/

