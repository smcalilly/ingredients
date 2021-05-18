## snippets

lists all the devices in the /dev directory that start with `cu.` and `tty.`
```bash
ls /dev/{tty,cu}.*
```

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
