# Deploying Instructions

These instructions are based on the [instructions](http://central.sonatype.org/pages/ossrh-guide.html)
for deploying to the Central Repository using [Maven](http://central.sonatype.org/pages/apache-maven.html).
Note that this is for Zup internal use only.

Once you've got that in place, you should be able to do deployment using the following commands:

```
# deploy snapshot version
mvn clean deploy # -Prelease to test signing

# make and deploy a release
mvn release:clean release:prepare -Prelease
mvn release:perform -Prelease
```

