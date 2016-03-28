Python One liner
================


* Display XML in pretty print format ::

  $ cat filename.xml | python -c 'import sys;import xml.dom.minidom;s=sys.stdin.read();print xml.dom.minidom.parseString(s).toprettyxml()'
