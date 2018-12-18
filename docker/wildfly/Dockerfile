FROM jboss/wildfly

USER root

COPY wait.sh /usr/local/bin/

RUN chmod +x /usr/local/bin/wait.sh && \
    yum -y install bash mysql-connector-java mysql dos2unix && \
    yum clean all && \
    rm -rf /var/cache/yum /var/log/yum.log &&\
    dos2unix /usr/local/bin/wait.sh

USER jboss
RUN  mkdir -p /opt/jboss/tmp

COPY wildflyconf.cli /opt/jboss/tmp/

RUN /opt/jboss/wildfly/bin/add-user.sh --user root --password root
RUN rm -rf /opt/jboss/wildfly/standalone/configuration/standalone_xml_history/current/*

RUN /opt/jboss/wildfly/bin/jboss-cli.sh --file=/opt/jboss/tmp/wildflyconf.cli && rm -rf /opt/jboss/tmp/

EXPOSE 8080 9990 8787
CMD ["/usr/local/bin/wait.sh"]