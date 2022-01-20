---
content_type: page
parent_title: Readings
parent_uid: aa632f83-51fe-4fa5-8aaf-1513de806253
title: Binary Search Trees
uid: 3e392c68-f217-c957-d2c8-70f39c63c084
---

tt { font-size: 1.3em; } div.maintabletemplate table caption { color: #a33033; font-size: 1em; font-family: Verdana, Arial, Helvetica, sans-serif; } div pre { margin: 10px 0px 10px 0px; padding: 15px 0px 15px 15px; background-color: #eeeeee; border: thin dotted #33CCFF; font-size: 1.1em; }

This page contains various implementations of different Binary Search Trees (BSTs).

Simple BST (no balancing)
-------------------------

*   [bst.py (PY)]({{< baseurl >}}/resources/bst)
    *   Features: insert, find, delete\_min, ASCII art
*   [bstsize.py (PY)]({{< baseurl >}}/resources/bstsize)
    *   Imports and extends bst.py
    *   Augmentation to compute subtree sizes
*   [bstsize\_r.py (PY)]({{< baseurl >}}/resources/bstsize_r)
    *   Recursive version from recitation for computing subtree sizes
    *   Features: insert, find, rank, delete

AVL tree
--------

*   [avl.py (PY)]({{< baseurl >}}/resources/avl)
    *   Imports and extends bst.py
    *   Features: insert, find, delete\_min, ASCII art

Testing
-------

Both bst.py and avl.py (as well as bstsize.py) can be tested interactively from a UNIX shell as follows:

*   python bst.py 10 — do 10 random insertions, printing BST at each step
*   python avl.py 10 — do 10 random insertions, printing AVL tree at each step

Alternatively, you can use them from a Python shell as follows:

\>>> import bst
>>> t = bst.BST()
>>> print t

>>> for i in range(4):
...   t.insert(i);
...
>>> print t
0
/\\
 1
 /\\
  2
  /\\
   3
   /\\
>>> t.delete\_min()
>>> print t
1
/\\
 2
 /\\
  3
  /\\

\>>> import avl
>>> t = avl.AVL()
>>> print t

>>> for i in range(4):
...   t.insert(i);
...
>>> print t
  1
 / \\
0  2
/\\ /\\
    3
    /\\
>>> t.delete\_min()
>>> print t
  2
 / \\
1  3
/\\ /\\