## snippets
recall the command you ran (thanks hannah):
```bash
history | grep "heroku"
```

### docker
npm within a docker container:
```bash
docker-compose run --rm app npm install
```

list all the containers:
```bash
docker ps -a 
```

[for more explanations of some basic/often-used flags](https://stackoverflow.com/questions/59424979/docker-ps-is-empty-after-docker-run#answer-59424994)

## aliases for bash/zsh profile
```bash
alias dup="docker-compose up $1"
alias down="docker-compose down $1"
alias dpm="docker-compose run --rm app python manage.py $1"
alias dtest="docker-compose -f docker-compose.yml -f tests/docker-compose.yml run --rm app"
```

