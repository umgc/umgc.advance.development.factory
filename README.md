# Advance Development Factory
---
As part of a diverse ecosystem of applications and technologies within software development, a need has been identified that standardizes the building, testing, and deployment of an organization's application suite. This repo Advance Development Factory sets the standard for developers  to build, test, and deployment of a diverse set of applications under a common framework that mitigates clients operating environment dependencies.

Docker image for dev environment.

# Use (local):
* Install Docker
* Clone Repo
* Build - docker build --pull --rm -f "docker/dockerfile" -t adf:latest "ADF" 
* Run -	docker run -dit -p 3389:3389 --rm --privileged adf:latest 

**Notes**:
* If on Linux/Mac, you can also use -p 3389:3389 to have it run on the default RDP port. In Windows, this port might not be available due to the built-in RDP server.
* The --privileged is needed for Chrome to run in Docker as well as nested virtualization support in Windows. The only alternative is running Chrome with the --no-sandbox flag. This requires more research, as there are security implications.
* Connect via RDP @ localhost:63389
* Clone repository to work with
* From repository run command code .

# TODO:
* Chrome crashes often

# Changelog:
Rob 8/24/2021
* Migrate to umgc.advance.development.factory

Rob 6/28/2021
* Change build order to keep most things cached during build and only rebuild items likely to change
* Remove second Dart Install command
* Convert CRLF -> LF
* Allow passwords to be passed in via environment variable

Jeroen 6/26/2021
* Add Welcome Screen

Jeroen 06/14/2021
* Fixed sound

Jeroen 06/13/2021
* Removed version A as X11 pass a no-go due to no sound, and difficulty on Windows.
* Renamed version B dir to ADF
* Set default password ('password') for developer, as passwordless login was not working on Linux.
* Set right terminal in update-alternatives so terminal button works.
* Added PulseAudio (does not seem to work yet)
* Added chmod 777 to start-up script. When built on Linux, the script on the local file system, and thus in the container is not executable.
* Commented out line that sets mirrors. Some mirrors were outdated, and this would halt the build.
* Updated readme, including comment about --privileged.
