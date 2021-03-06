# virtualenv a Flask

Na přednášce jsme ukazovali vlastní moduly, jak použít
moduly z PyPI a jak použít virtualenv.

Zkuste se podívat, zdali vůbec kde je na Vašem počítači modul 
[`flask`][flask] a v jaké je verzi a která verze je aktuální.

Pokud modul flask nebude v poslední verzi, nainstalujte ji
do [virtualenv][venv-guide].  Alternativně můžete použít 
i modernější [pipenv][pipenv-guide]. 

Na Windows zkuste [venv]

## Testovací aplikace

```python
import flask

from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello Flask! (flask v.{})".format(flask.__version__)
    
if __name__ == '__main__':
    app.run()
```

## Sample session transcript (Unix)

```bash

# create virtualenv

virtualenv -p python3 ~/my-flask

# activate

. ~/my-flask/bin/activate

# PS1 prompt is changed

# check pip and python

which python3
which pip 

# install flask

pip install flask

```

## Sample session transcript (Windows)

```commandline

# create my-flask virtualenv

python -m venv my-flask

# activate it

my-flask\activate.bat

# prompt should change

pip install flask

# check version

python3 -c 'import sys; print(sys.path)'

```

## Notes

Pokud chcete specifickou verzi Flasku, použijte

```bash
pip install 'flask==0.10'

# nebo

pip install 'flask>=0.11,<0.12'

```

[flask]: http://flask.pocoo.org
[venv-guide]: http://docs.python-guide.org/en/latest/dev/virtualenvs/#lower-level-virtualenv
[pipenv-guide]: http://docs.python-guide.org/en/latest/dev/virtualenvs/
[venv]: https://docs.python.org/3.5/library/venv.html