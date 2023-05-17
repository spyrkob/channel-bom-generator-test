### Create simple BOM
1. Deploy the manifest.yaml to local repository:
  `mvn deploy:deploy-file -Dfile=manifest.yaml -DgroupId=org.wildfly.prospero.test -DartifactId=test-manifest -Dversion=1.0.0 -Dclassifier=manifest -Dpackaging=yaml -Durl=file:test-repo`
2. Build the pom with
  `mvn clean install`

### Update version of jboss-logging
1. Edit the jboss-logmanager version manifest.yaml to
   ```yaml
   - groupId: org.jboss.logmanager
     artifactId: jboss-logmanager
     version: "2.1.18.Final"
   ```
2. Deploy the manifest.yaml to local repository with new version:
   `mvn deploy:deploy-file -Dfile=manifest.yaml -DgroupId=org.wildfly.prospero.test -DartifactId=test-manifest -Dversion=1.0.1 -Dclassifier=manifest -Dpackaging=yaml -Durl=file:test-repo`
3. Build the pom with
   `mvn clean install`

### Use URL to reference manifest
1. Edit the pom.xml replacing channel definition with
   ```
   <channels>
     <channel>
       <manifest>
         <url>file:manifest.yaml</groupId>
       </manifest>
     </channel>
   </channels>
   ```
2. Build the pom with
   `mvn clean install`

## Resetting environment
To reuse version `1.0.0` of the manifest, the local cached version of it has to be removed: `rm -rf ~/.m2/repository/org/wildfly/prospero/test/`