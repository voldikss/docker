FROM atlassian/jira-software:8.20

USER root

COPY atlassian-agent.jar /opt/atlassian/jira/

# COPY mysql-connector-j-8.0.32.jar /opt/atlassian/jira/lib/mysql-connector-j-8.0.32.jar

RUN echo 'export JAVA_OPTS="-javaagent:/opt/atlassian/jira/atlassian-agent.jar ${JAVA_OPTS}"' >> /opt/atlassian/jira/bin/setenv.sh
