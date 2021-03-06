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

### Structure of results
 - `[x]gb` # x: aprox size of db tested

   -- `v[x]m[y]g[z]` # x: cpus, y: cpu mem, z: number of k80 gpus

### Table schema
```bash
CREATE TABLE variants (VARIANT TEXT ENCODING DICT, CHROMOSOME TEXT ENCODING DICT(8), c3_START BIGINT , c4_REF TEXT ENCODING DICT , ALT TEXT ENCODING DICT , RSID TEXT ENCODING DICT , AC SMALLINT , AF FLOAT , nCalled SMALLINT , nNotCalled SMALLINT , nHomRef SMALLINT , nHet SMALLINT , nHomVar SMALLINT , TYPE TEXT ENCODING DICT(8) );
```
