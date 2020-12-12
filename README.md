# templify-docker
Generates files from templates with Jinja2


# Requirements
python3
jinija2

# Usage
In your Dockerfile include python3 and jinja2.

### Example
```
RUN apt update && apt install -y python3 python3-jinja2
```

Then you can call template.py from bash or any other script language in your entrypoint file.

### Example
#### Bash
```
DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" >/dev/null 2>&1 && pwd )"
template () {
    python3 $DIR/template.py --template $DIR/superawesome.conf.j2 --output /etc/superawesome/superawesome.conf
}
template
```
