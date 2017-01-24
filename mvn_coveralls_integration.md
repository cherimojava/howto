This document provides you with the needed information to setup coveralls reporting for your repository.

First you need to visit the coveralls.io website and enable the coveralls integration for the given repository of orchida:

![Coveralls Repository View](/pictures/enable_repo_coveralls.png)

You might need to sync repos first, if they where just recently created or you got permissions to them. You find the button to this near the end of the page, looking like:

![Coveralls Repository Refresh](/pictures/sync_coveralls_repos.png)

Once this is done extend your `.travis.yml` maven build command to contain the following commands:

```
test jacoco:report coveralls:report
```

This will run the jacoco test report, which will be reported back to coveralls. Once that's done, don't forget to add the coveralls badge to your Readme.md.
