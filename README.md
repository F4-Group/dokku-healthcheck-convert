# dokku-healthcheck-convert

Automatically generates app.json from CHECKS file, if no app.json exists, and removes CHECKS file.

Using convert tool from https://github.com/dokku/docker-container-healthchecker#convert-command and applying custom fixes.

Fixes includes 
- setting attempts to 6, to match pre v0.32 5 retries (down to 1 after v0.32)
- trimming spaces from checked content

This allows to convert apps from CHECKS files to app.json later.

## Requirements
- dokku 0.34.4+
- docker 1.8.x

## Limitations

Only works on source code apps, not on image.

## Installation

`dokku plugin:install https://github.com/F4-Group/dokku-healthcheck-convert --name 00-dokku-healthcheck-convert`

Plugin name must be before `app-json` so it runs before it.
