# AT-SPI

AT-SPI (_Assistive Technology Service Provider Interface_): Es un framework de accesibilidad independiente de plataforma que proporciona comunicación entre las tecnologías de apoyo o de asistencia (AT, del inglés Assistive Technologies) y las aplicaciones.

## e2e v1

```py
#!/usr/bin/env python3
import gi
gi.require_version("Atspi", "2.0")
from gi.repository import Atspi

import subprocess

p = subprocess.Popen("./hello.py")

desktop = Atspi.get_desktop(0)

def children(obj):
    for i in range(0, obj.get_child_count()):
        yield i, obj.get_child_at_index(i)

app = [child for _, child in children(desktop) if child and child.get_name() == "hello.py"][-1]

[child.get_name() for _, child in children(app)]

assert any(child.get_name() == "Hello World" for _, child in children(app))
```

## e2e v2

```py
#!/usr/bin/env python3
import gi
gi.require_version("Atspi", "2.0")
from gi.repository import Atspi

def children(obj):
    for i in range(0, obj.get_child_count()):
        yield i, obj.get_child_at_index(i)

import subprocess
import time

def run(path, name = None):
    name = name or "nombre único"
    subprocess.Popen([path, "--name", name])
    desktop = Atspi.get_desktop(0)
    start = time.time()
    timeout = 5
    app = None
    while app is None and time.time() - start < timeout:
        app = next((child for _, child in children(desktop) if child and child.get_name() == name), None)
        if app is None:
            time.sleep(0.6)
    return app

def tree(obj, path = ()):
    yield path, obj
    for i, child in children(obj):
        yield from tree(child, path + (i,))

def dump_tree(obj):
    for path, node in tree(obj):
        print("  "*len(path), path, " ", f"{node.get_role_name()}({node.get_name()})", sep = "")
```

## e2e v3

```py
#!/usr/bin/env python3
import subprocess
import time
from collections import namedtuple
import sys
import random

import gi
gi.require_version("Atspi", "2.0")
from gi.repository import Atspi

def run(path, name = None):
    name = name or f"{path}-test-{str(random.randint(0, 10**8))}"
    process = subprocess.Popen([path, "--name", name])
    desktop = Atspi.get_desktop(0)
    start = time.time()
    timeout = 5
    app = None
    while app is None and (time.time() - start) < timeout:
        gen = (child for _, child in children(desktop) if child and child.get_name() == name)
        app = next(gen, None)
        if app is None:
            time.sleep(0.6)
    return (process, app)

def stop(process):
    if process is not None:
        process.kill()

def children(obj):
    for i in range(0, obj.get_child_count()):
        yield i, obj.get_child_at_index(i)

def tree(obj, path = ()):
    yield path, obj
    for i, child in children(obj):
        yield from tree(child, path + (i,))

def do_action(obj, name):
    for i in range(0, obj.get_n_actions())
        if obj.get_action_name(i) == name:
            obj.do_action(i)
            return
    raise RuntimeError(f"{obj} no tiene una acción {name}")
```

## **e2e**

```py
#!/usr/bin/env python3
import subprocess
import time
from collections import namedtuple
import textwrap
import random

import gi
gi.require_version('Atspi', '2.0')
from gi.repository import Atspi


# Contexto de las pruebas
Ctx = namedtuple("Ctx", "path process app")


# Funciones de ayuda
def show(text):
    print(textwrap.dedent(text))

def show_passed():
    print('\033[92m',"    Passed", '\033[0m')

def show_not_passed(e):
    print('\033[91m',"    Not passed", '\033[0m')
    print(textwrap.indent(str(e), "   "))


def get_app(name):
    desktop = Atspi.get_desktop(0)
    start = time.time()
    timeout = 5
    app = None
    while app is None and (time.time() - start) < timeout:
        gen = (child for _i, child in children(desktop) if child and child.get_name() == name)
        app = next(gen, None)
        if app is None:
            time.sleep(0.6)
    return app

def get_obj(parent, role= None, name= None):
    def _check(obj):
        return role is None or obj.get_role_name() == role and \
            name is None or obj.get_name() == name
    return next((obj for _, obj in tree(parent) if _check(obj)), None)

def run(path, name= None):
    name = name or f"{path}-test-{str(random.randint(0, 100000000))}"
    process = subprocess.Popen([path, '--name', name])
    app = get_app(name)
    return (process, app)

def stop(process):
    if process is not None:
        process.kill()


# Funciones de acceso a at-spi
def children(obj):
    for i in range(0, obj.get_child_count()):
        yield i, obj.get_child_at_index(i)

def tree(object, path= ()):
    yield path, object
    for i, child in children(object):
        yield from tree(child, path + (i,))

def do_action(obj, name):
    for i in range(0, obj.get_n_actions()):
        if obj.get_action_name(i) == name:
            obj.do_action(i)
            return
    raise RuntimeError(f"{obj} no tiene una acción {name}")
```
