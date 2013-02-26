update-combine
==============

A small tool written in Python to actively merge JavaScript files in a directory.


Purpose
-------


Usage
-----

Place updateCombine.py in a directory with (or without) *.js files that you wish to be automatically combined.
To run indefinitely:

```python updateCombine.py```

To watch a directory other than `./` (relative to updateCombine.py):

```python updateCombine.py relative_path_to_dir```

It may be useful to actively merge source files while running a local dev server. This can be accomplished easily by running update-combine and python's SimpleHTTPServer in separate threads.

```python
import subprocess, SimpleHTTPServer, SocketServer, threading

Handler = SimpleHTTPServer.SimpleHTTPRequestHandler
httpd = SocketServer.TCPServer(("", 8000), Handler)

serve = threading.Thread(target=httpd.serve_forever)
serve.start()
subprocess.call(['python','updateCombine.py'])
```







