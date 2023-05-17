Create simple BOM
1. Build the pom with
  `mvn clean install`

Update version of jboss-logging
1. Edit the jboss-logmanager version manifest.yaml to
```yaml
  - groupId: org.jboss.logmanager
    artifactId: jboss-logmanager
    version: "2.1.18.Final"
```
2. Build the pom with
   `mvn clean install`