version: '3.8'

services:
  jenkins-agent:
    image: jenkins/ssh-agent:alpine-jdk17
    container_name: jenkins-agent
    ports:
      - "2200:22"
    environment:
      JENKINS_AGENT_SSH_PUBKEY: "ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAILQfd/usUPArQ3tXY50HZzKSHb9oTm/+hHSXZeF+tGz3 root@ip-172-31-15-55"
    volumes:
      - agent-data:/home/jenkins/agent

volumes:
  agent-data:
