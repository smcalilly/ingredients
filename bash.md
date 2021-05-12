## snippets

### docker
npm within a docker container:
```bash
docker-compose run --rm app npm install
```

list all the containers (not only the running ones):
```bash
docker ps -a 
```

debug your image:
```bash
docker logs <my-container-image>
```

- [for more explanations of some basic/often-used flags](https://stackoverflow.com/questions/59424979/docker-ps-is-empty-after-docker-run#answer-59424994)

- ["image" vs "container"](https://stackoverflow.com/questions/23735149/what-is-the-difference-between-a-docker-image-and-a-container) (hint: a container is an instance of an image. or as stackoverflow [username Julien said](https://stackoverflow.com/questions/23735149/what-is-the-difference-between-a-docker-image-and-a-container#comment-79144517), "the image is the recipe, the container is the cake ;-) you can make as many cakes as you like with a given recipe")


## aliases for bash/zsh profile
```bash
# aliases
alias dpm="docker-compose run --rm app python manage.py $1"
alias dup="docker-compose up $1"
alias down="docker-compose down $1"
alias dtest="docker-compose -f docker-compose.yml -f tests/docker-compose.yml r$
alias dbuild="docker-compose build"
```

refresh after changes
```bash
source ~/.bashrc
```

```zsh
source ~/.zshrc
```

usage
```bash
dpm shell # same as docker-compose run --rm app python manage.py shell
dup --build # same as docker-compose up --build
```
