## Example Mocked-Up gitlab-ci file (not tested)

```yml
stages:
  - daily
  - build
  - test
  - deploy

sync_live_uctech_for_siteimprove_crawl:
  stage: daily
  script:
    - "terminus auth:login --machine-token=$TOKEN && terminus env:clone-content uctech-ucsb-edu-v04.live uctech-ucsb-edu-v04.siteimprove"
  allow_failure: true
```

## Get a generated Pantheon token for use in Gitlab

```txt
Your new machine token is ready
Device Name
uctech-ucsb-idgitlab-ci
Machine Token
***
This token is generated for use but can only be viewed once for security purposes. Once you leave this screen you will not be able to view the token.

Run this Terminus command in your terminal to authenticate

terminus auth:login --machine-token=****
```

## Example of Running the proposed solution in straight Docker-Compose (not Gitlab-CI)

```txt
wodby@terminus.container:~/vendor/pantheon-systems/terminus/bin $ php terminus auth:login --machine-token=3WUJ2GUHmWI2znhgi_c-mbZ4zTJ1ks8SOALkoYmshAZbI && php terminus env:clone-content uctech-ucsb-edu-v04.live siteimprove -y
 [notice] Logging in via machine token.
 [notice] Cloning files from live environment to siteimprove environment
 [notice] Cloned files from "live" to "siteimprove"
 [notice] Cloning database from live environment to siteimprove environment
 [notice] Cloned database from "live" to "siteimprove"
wodby@terminus.container:~/vendor/pantheon-systems/terminus/bin $ 
```
