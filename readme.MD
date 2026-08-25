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

**Technical Debt:**
It is the estimated time required to fix all maintainability issues (code smells) in the codebase. That future pain = technical debt

**Example:**
Your project has:
100 code smells
Each smell estimated as 10 minutes to fix
```
Technical Debt = 100 × 10 min = 1000 minutes ≈ 16.6 hours
```

Example timings SonarQube assumes: <br/>
Rename variable → 2 min <br/>
Reduce complexity → 30 min <br/>
Remove duplication → 1h

### 📋 Duplication
Percentage or blocks of identical or near-identical code across files. copy-paste risk. Should be made as function and reuse it.

### 📊 Coverage

Percentage of code that is executed by unit tests.
```
Coverage = (Lines covered by tests / Lines to cover) × 100
```

Unit testing will give us a JSON report
* Total test cases executed
* How many passed, How many failed

This report should be uploaded to SonarQube server through agent.

### 🔒 Security Rating
Rating based on severity of vulnerabilities

**Ratings logic:**
A → No vulnerabilities
B–E → Based on highest severity found

Example:
1 Critical vulnerability → Rating becomes E <br/>
Security Rating = worst vulnerability decides

