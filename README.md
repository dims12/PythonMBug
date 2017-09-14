# Python -m bug

`python -m` processes "root" package differently, than inner packages.

Download the following project and run

    python -m package1.script

from root project directory. You will see output

    package1 init
    package1/script.py

this means, that Python ran both `script.py` and `__init__.py` files.

Now run 

    python -m script
    
from root project directory.  

Logically it is the same: run module named `script` from some package, which is not root one.

Unfortunately, Python doesn't run `__init__py` this time and you will see just

    script