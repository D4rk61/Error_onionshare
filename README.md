# Error_onionshare
(Resuelto) Error de onionshare al ejecutarse

<br>

Al ejecutar Onionshare para hacer una subida de documentos me tope con el siguiente error:

<br>




  ``` bash
    /usr/bin > python3 onionshare-cli  
  Traceback (most recent call last):
  File "/usr/bin/onionshare-cli", line 33, in <module>
    sys.exit(load_entry_point('onionshare-cli==2.5', 'console_scripts', 'onionshare-cli')())
  File "/usr/bin/onionshare-cli", line 25, in importlib_load_entry_point
    return next(matches).load()
  File "/usr/lib/python3.10/importlib/metadata/__init__.py", line 171, in load
    module = import_module(match.group('module'))
  File "/usr/lib/python3.10/importlib/__init__.py", line 126, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
  File "<frozen importlib._bootstrap>", line 1050, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1027, in _find_and_load
  File "<frozen importlib._bootstrap>", line 1006, in _find_and_load_unlocked
  File "<frozen importlib._bootstrap>", line 688, in _load_unlocked
  File "<frozen importlib._bootstrap_external>", line 883, in exec_module
  File "<frozen importlib._bootstrap>", line 241, in _call_with_frames_removed
  File "/usr/lib/python3.10/site-packages/onionshare_cli/__init__.py", line 30, in <module>
    from .web import Web
  File "/usr/lib/python3.10/site-packages/onionshare_cli/web/__init__.py", line 21, in <module>
    from .web import Web
  File "/usr/lib/python3.10/site-packages/onionshare_cli/web/web.py", line 28, in <module>
    import flask
  File "/home/evildr4gon/.local/lib/python3.10/site-packages/flask/__init__.py", line 19, in <module>
    from jinja2 import Markup, escape
ImportError: cannot import name 'Markup' from 'jinja2' (/usr/lib/python3.10/site-packages/jinja2/__init__.py)

  
  ```
  <br>
  
  
  **Este se da por tener una version del paquete "Flask" Desactualizada**
  
  <br>
  
  
  ---
  
  ## Solucion
  
  En muchos foros habian respuestas algo confusas en su mayor parte y en ingles asi que aqui traigo la solucion sencilla o por lo menos mas entendible, en muchas ocaciones al instalar otros programas podemos romper las **dependecias** de un paquete, por ende dejando inutil a otros programas, bueno en este caso tendriamos que instlar una version de flask
  
<br>


``` bash 
  !w /usr/bin > pip show flask  
  Name: Flask
  Version: 0.12.1

```
  
  
Esta version de flask nos dara conflico, tendremos que ejecutar el siguiente comando:

``` bash 
  pip install flask==2.0.3        
```

<br>

**Acto seguido actualizamos o reinstalamos onionshare y listo ya estara con las dependencias corregidas**


  
