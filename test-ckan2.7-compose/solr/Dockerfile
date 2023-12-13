FROM solr:6.2-alpine
MAINTAINER Open Knowledge

# Enviroment
ENV SOLR_CORE ckan
# Adjust to your needs
ENV CKAN_VERSION dev-v2.8

# User
USER root

# Create Directories
RUN mkdir -p /opt/solr/server/solr/$SOLR_CORE/conf
RUN mkdir -p /opt/solr/server/solr/$SOLR_CORE/data

# Adding Files
COPY solrconfig.xml \
schema.xml \
currency.xml \
synonyms.txt \
stopwords.txt \
protwords.txt \
elevate.xml \
/opt/solr/server/solr/$SOLR_CORE/conf/

# Create Core.properties
RUN echo name=$SOLR_CORE > /opt/solr/server/solr/$SOLR_CORE/core.properties

# Giving ownership to Solr
RUN chown -R $SOLR_USER:$SOLR_USER /opt/solr/server/solr/$SOLR_CORE
