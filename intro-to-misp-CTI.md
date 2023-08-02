![MISP logo](./pictures/misp-logo.png)

# MISP micro training for analysts CTI (draft you can edit for your own training)

# Intro part 1 
------------------------------------
Agenda for this first part:

1.  practical usage from user perspective
1.  MISP project
1.  sharing communities
1.  data model
2.  taxonomies

Full slide deck available from MISP training at : https://github.com/MISP/misp-training

## 1. Practical usage from user perspective

**What can I do?**
- collect indicators of compromised -> feed, free text import
- write reports -> export
- share informations with analysts -> sharing
- preparing information to share with clients (over a MISP synchronisation for example) -> sharing, tagging
- Using MISP objects and attributs -> data model
- integrate continuous stream of information -> feeds
- work with correlations -> use data
	- what is a correlation in intelligence analysis?
	- what a correlation is not in intel analysis?
	- use correlation in MISP in order to:
			- corroborate findings
			- reinforce analysis
			- confirm a specific aspect
			- identify new threat in your community

### Examples
Operational security
- searching & validating for indicators
Intelligence analysts
- information gathering about adversary groups
  gather informations about campaigns and attack:
	- are they related?
	- who is targeting me?
	- who are the adversaries?

## 2. What is MISP project

- MISP project includes **best practices** (for data flow, sharing) in information sharing and **open standards** for importing and exporting data.


Misp project includes:
- a large community of Misp users and contributors
- opensource software
- an intelligence practice and knowledge database
- open standards
- the possibility to join and build a sharing community

Important:
- MISP is opensource
- you can work with MISP modules to add expansions, export and import functionalities to MISP


## 3. Sharing communities 

(?) What is a user group?

MISP is used among different user groups:
- trusted groups
- financial sectors
- military and international org
- security vendors

Members of a sharing communities can be:
- consumer
- contributor
- producer 
...of "information" 


## 4. Data model: Events, objects, attributes & galaxies

### Templates and contextualization 

- Analysis with MISP is based on **"contextualy linked information"**
- MISP uses **templates** (object templates) to help the users to extend data models in MISP

- **galaxies** are used for the categorization of data and for more granularity (ex: threat actors, TTPs)

### Indicators and attributes

**Indicators:**
- "a pattern that can be used to detect suspicious or malicious cyber activity"

**Attributes:**
- Can be network indicators, system indicators, or any non-technical information ex forensics ex:[banking]("https://www.misp-project.org/taxonomies.html#_financial")
- Attributes are **relative to an event** in MISP
- attributes can be grouped into an **object**

**When you create an attribute you can add:**
- the type: ex MD5 how is the information encoded
- the category: payload delivery
- if it has an IDS flag (is it used in an IDS)
-  ...

### Events

Events have an **uuid**, an owner org and a **creator org**. 

Events can be found in your MISP instance by searching by uuid (or via the url and by adding the uuid of the event), or by keyword search.

While creating an event, you are asked to specify a **tagging** (if needed) and a **sharing parameter.**

|**event data model**|
|-|
|creator org|
|description|
|analysis|
|threat level|
|distribution|

### Events: Classification with tagging 
- use it to be efficient, **avoid NOISE**
- tagging scheme exists in taxonomies, your own can be created (ex: a client can have his own tagging scheme and taxonomies)

### Events: Sharing 

Creator of the event decide the sharing parameter of the event. 
- [distribution typology]
	- your organisation only
	- this community only 
	- connected communities
	- all communities
	- sharing group*

## 5. Taxonomies

**ex: -> Classification of threat indicators**

- tags 
- machine tags (triple tag) 
	- NAMESPACE PREDICATE VALUE 

admiralty-scale:source-reliability="c"

|admiralty-scale|source-reliability|"c"|
|-|-|-|
|namepsace|predicate|value|

### Taxonomies

- implemented in JSON format
- taxonomies are in an independant Git [repository](github.com/MISP/misp-taxonomies)

|some existing taxonomies|
|-|
|NATO - Admiralty Scale|
|CIRCL Taxonomy - Schemes of Classification in Incident|
|Response and Detection|
|eCSIRT and IntelMQ incident classification|
|EUCI EU classified information marking |
|Information Security Marking Metadata from DNI (Director of National Intelligence - US)|
|NATO Classification Marking |
|OSINT Open Source Intelligence - Classification|
|TLP - Traffic Light Protocol|
|Vocabulary for Event Recording and Incident Sharing - VERIS|
|and many more like ENISA, Europol, or the draft FIRST SIGInformation Exchange Policy.|


taxonomies create tags:
example the distribution of events among MISP instances
(push rules)

manage taxonomies with PyTaxonomies (Python 3 module)


## Q&A

https://github.com/MISP/MISP

https://github.com/MISP/misp-taxonomies

https://github.com/MISP/PyTaxonomies

https://github.com/MISP/misp-warninglists

info@circl.lu (if you want to join one of the MISP community
operated by CIRCL)

PGP key fingerprint: CA57 2205 C002 4E06 BA70 BE89 EAAD
CFFC 22BD 4CD5

# Intro part 2             
# Get you hands dirty, general usage part 1:
Check once view and understood:
1. - [ ] installing and running a MISP VM
1. - [ ] create and populate an event
1. - [ ] viewing data
1. - [ ] export and API
2. - [ ] synchronisation 

## 1. Install a MISP VM

### Install and run a MISP
download from last image (circl.lu/misp-images/latest)
creds for machine:
	- MISP admin: admin@admin.test
	- SSH: misp/Password1234
- first thing you are asked to do is to change the password.
- secondly you will create an organisation and a user.
- then you'll log into MISP with this new user account.

## 2. Create and populate an event 
- add attribute, **batch add** (import multiple to creation of unique attributes)
	- explanation: ip list, if mixed list with ip and domains, use free-text import
- adding objects, object template 
- **freetext import**
- other imports
- consulting available templates
- add attachments

**What is done** when importing attributes:
- automatic correlation
- input mod via validation (regex)
- tagging

publishing
- with and without an email (send a notification email or not)
- via the API(**)
- the case of delegation

## 3. Viewing data

There are 4 important points to start:
- Correlation graphs
- download data in various formats (at freetext import or from you?)

## 4. Exports and API

- download an event from MISP: multiple formats
- API* (for automatic publication)
- **Download search results**
- case of **cached exports**

# MISP general usage part 2
Check once view and understood:

1. - [ ] synchronization
1. - [ ] feeds
1. - [ ] collaborating
1. - [ ] MISP basic admin
1. - [ ] MISP modules
1. - [ ] PyMISP


## 1. Synchronization 

Distribution typology, see above 4.3 Event sharing 
- sync connection
- push/pull model
- filter the sync (ex: filter by tag or by org)
- testing 
- **cherry pick**

## 2. Feeds 

feeds formats:
- MISP
- Freetext
- CSV

- adding/ editing feeds
- previewing feeds
- local vs network feeds


## 4. Basic MISP admin 
### Normalization 

Normalizing OSINT and private feeds: any normalization is done **before pushing data into a MISP**

We use **warning lists** at the exportation of data 

|IMPORT|
|-|
|normalizing external input and feed into MISP (feed importer)|
|comparing feeds: similarities, false pos|

|EXPORTATION|
|-|
|make warning lists for content to evaluate (quality)|
|make warning list to avoid false positive associated with well known indicators (JSON file)|

- How to activate feeds
- How to activate modules in MISP
- Workers

see part SIEM integration 

## 5. MISP modules
Existing MISP modules ex:
- Viper
	- CLI for Passive SSL
	- CLI for Passive DNS
- VirusTotal
- mail to MISP (for importing IOC)

### Expanding MISP 
 
 API: **PyMISP**, API : no integration with the UI
 
 Three types of modules:
- Expansion modules
- Import modules
- Export modules

## 6. PyMISP

**PyMISP usage example**: See [How to make a MISP import script](https://www.misp-project.org/2020/09/30/How-To-Make-A-MISP-Import-Script.html)


## extra things, TDL (to do later)
### MISP admin training with MISP VM 

https://www.circl.lu/misp-training

 
 ### MISP module, UI configuration
 
 activate the modules
 Go Server Settings : Enrichment 
