# mapd-load-testing

Simple [artillery](https://artillery.io/docs/) test script and results run against different mapd
configurations with our expected database


### Usage
install artillery
```bash
npm install -g artillery
```

update [load-test.yml](load-test.yml) target and phase parameters.

run load test (-k will ignore https errors )
```bash
artillery run -k load-test.yml -o result.json
```

generate a HTML report
```bash
artillery report result.json
```
