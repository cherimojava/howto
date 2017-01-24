To enable caching of maven artefacts in travis, you should include this into your `.travis.yml`

```yml
cache:
  directories:
    - '$HOME/.m2/repository'
```
