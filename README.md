# Simple git www server

An apache web server that periodically pulls and updates it's code from a git repository.

### Environmenet Variables
| name | default | description |
| --- | --- | --- |
| GIT_REPO | `none` | The git repository to pull the code from. The files contained in this repository will be placed directly into the web root of the apache server |
| GIT_BRANCH | `main` | The branch to clone |
| GIT_INTERVAL | `300` | How often to wait in seconds before checking for new changes |

### Usage
```
docker build -t simplegitwww .
docker run -d -p 8080:80 -e GIT_REPO="https://github.com/mdusher/mdusher.github.io.git" simplegitwww
```
Then visit http://localhost:8080