This document will provide you with the needed steps to setup Travis-ci builds to publish builds into Sonatype OSS Repository.

Add the following `settings.xml`to your project root:

```xml
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 http://maven.apache.org/xsd/settings-1.0.0.xsd">
    <servers>
        <server>
            <id>sonatype-nexus-snapshots</id>
            <username>${env.CI_DEPLOY_USERNAME}</username>
            <password>${env.CI_DEPLOY_PASSWORD}</password>
        </server>
    </servers>
</settings>
```
Next add this to your `.travis.yml` to use a custom build script using the just created config:

```yml
script: "mvn deploy --settings settings.xml"
```

Following configure the environment variables within the repository environment variables section, *make sure to not expose the variable values*.

* CI_DEPLOY_PASSWORD
* CI_DEPLOY_USERNAME

After that you're ready to deploy artifacts with each successful build of the job. Don't forget to include the travis-ci badge to show off your successful travis builds.
