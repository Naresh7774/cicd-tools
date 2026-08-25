### Jenkins Setup

Installation commands from Jenkins official doc
```
sudo curl -o /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
# Add required dependencies for the jenkins package
sudo yum install fontconfig java-21-openjdk -y
sudo yum install jenkins -y
sudo systemctl daemon-reload
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

#### Plugins:
* Stage view
* AWS Steps
* SonarQube scanner
* Pipeline utility steps

#### Master Agent Architecture
* Create credentials to connect agent
* Install Java in agent
* Select Non verification strategy

#### Credentials
* SSH authentication
* AWS credentials
* Sonar token

# Sonar

### 🐞 Bugs

An issue representing a coding error that will likely cause unexpected behavior or application failure. This seems fine but sometimes it may break in production.

### 🔐 Vulnerabilities
A security-related holes that can be exploited by attackers. This can be hacked

### 👃 Code Smells
A maintainability issue that does not break the app but makes the code hard to understand, change, or maintain. This works today, but hurts tomorrow
