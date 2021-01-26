# GTK3

## hello

```py
#!/usr/bin/env python3
import gi
gi.require_version("Gtk", "3.0")
from gi.repository import Gtk

window = Gtk.Window(title="Hello World")
window.show()
window.connect("destroy", Gtk.main_quit)
Gtk.main()
```

## gtk en ipython

```py
# Instrucción mágica para realizar Gtk.main() de forma asíncrona
# y continuar trabajando viendo cambios de la interfaz en directo.
%gui gtk3
```
