# LiC-docker
Docker image builder for the LiC software. Based on the eXist-db Docker image [https://hub.docker.com/r/existdb/existdb]. 

### This image pre-loads the following eXist-db libraries and modules: 
1. EXPATH Cryptographic Library Module v0.6 [http://exist-db.org/exist/apps/public-repo/packages/expath-crypto-exist-lib.html?eXist-db-min-version=4.4.0]
2. FunctX library [http://exist-db.org/exist/apps/public-repo/packages/functx.html]
3. SPARQL and RDF indexing for eXist-db [http://exist-db.org/exist/apps/public-repo/packages/exist-sparql.html?eXist-db-min-version=3.0.3]

### Additional Customizations
1. The image also includes a custom controller-config.xml and exist-webapp-context.xml to set the Srophe app (/db/apps/srophe) as the root direcory, allowing users to access the application home page at http://localhost:8080/index.html. 
2. A custom eXist-db conf.xml adds the RDF index collection.xconf used by the SPARQL module. 

## How To Use
Build a up to date version of the LiC application [https://github.com/LiteratureInContext/LiC-app] and data repositories [https://github.com/LiteratureInContext/LiC-data]
Move the new .xar files into the autodeploy directory. 

Build your new docker image: 
docker build --platform linux/amd64 -t lic .




