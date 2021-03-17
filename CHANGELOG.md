# Changelog


<!--
## [x.x.x] - yyyy-mm-dd
### Added       : for new features.
### Changed     : for changes in existing functionality.
### Deprecated  : for soon-to-be removed features.
### Removed     : for now removed features.
### Fixed       : for any bug fixes.
### Security    : in case of vulnerabilities.
-->
Install python libraries. 
```python
pip install -r requirements.txt
```

## [1.0.0] - 2021-03-16
### commentary
This project is to spin up a Mongo instance in a docker container with persistant data in a volume named mongodata with 500 example documents in sandbox.businessReviews.

If the data needs to be reset you will have to remove the attached volume, this way the mongo-init.js will run.
```docker
docker-compose down
docker-compose pull
docker volume rm 'dockermongo_windows_mongodata'
docker-compose up -d
```

### Addeed
- docker-compose.yml
- mongo-init.js
- .env
- .gitignore
- requirements.txt
- sample data 
- readme.md

### Notes
Had to create a volume to store data.  Could not figure out how to map to a windows directory
``` docker
docker volume create --name=mongodata
```

Remove all dangling volumes.
``` docker
docker volume rm $(docker volume ls -qf dangling=true)
```
---
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).