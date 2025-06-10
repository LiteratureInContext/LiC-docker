# srophe-docker
Docker image builder for the Srophe software. Based on the eXist-db Docker image [https://hub.docker.com/r/existdb/existdb]. 

### This image pre-loads the following eXist-db libraries and modules: 
1. EXPATH Cryptographic Library Module v0.6 [http://exist-db.org/exist/apps/public-repo/packages/expath-crypto-exist-lib.html?eXist-db-min-version=4.4.0]
2. FunctX library [http://exist-db.org/exist/apps/public-repo/packages/functx.html]
3. SPARQL and RDF indexing for eXist-db [http://exist-db.org/exist/apps/public-repo/packages/exist-sparql.html?eXist-db-min-version=3.0.3]

### Additional Customizations
1. The image also includes a custom controller-config.xml and exist-webapp-context.xml to set the Srophe app (/db/apps/srophe) as the root direcory, allowing users to access the application home page at http://localhost:8080/index.html. 
2. A custom eXist-db conf.xml adds the RDF index collection.xconf used by the SPARQL module. 

## How To Use
Pre-built images are available on DockerHub [].

This repository uses GitHub submodules [https://git-scm.com/book/en/v2/Git-Tools-Submodules] to load the most recent version of the Srophe application and the Syriaca.org data. In order to build the application
and data packages you must explicitly pull the submodules when you clone the repository, and before rebuilding the image: 

Build the docker file
```docker build -t srophe:v1.0 .```

## Sponsors:
The Center of Digital Humanities Research at Texas A&M University [http://codhr.dh.tamu.edu/]

Digital Cultural Heritage Cluster at Vanderbilt University [https://my.vanderbilt.edu/digitalculturalheritage/]

Syriaca.org: The Syriac Reference Portal [http://syriaca.org/]



