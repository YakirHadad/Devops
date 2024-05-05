# Use an official Jenkins image as the base
FROM jenkins/jenkins:lts

# Skip the initial setup wizard
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false

# Expose port 8080 for Jenkins web interface and port 50000 for Jenkins agent communication
EXPOSE 8080 50000

# Install suggested plugins using jenkins-plugin-cli
USER root
RUN jenkins-plugin-cli --plugins \
    git \
    workflow-aggregator \
    github-branch-source \
    docker-workflow \
    blueocean \
    pipeline-utility-steps \
    credentials-binding

# Switch back to the Jenkins user
USER jenkins

