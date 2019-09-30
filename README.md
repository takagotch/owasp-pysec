### owasp-pysec
---
https://github.com/ebranca/owasp-pysec

```py
// tests/io_tests/test_lines_file.py
import sys

import pysec
import pysec
import pysec.io
import pysec.iofcheck
import pysec.io.fd
import pysec.io.fs
import pysec.io.temp

def standard_read_self():
  test_data = []
  fd = open(__file__, "r")
  for line in fd:
    test_data.append(line)
  fd.close()
  return test_data

def main():
  sys.stdout.write("BASIC LINES TEST: ")
  
  
  with pysec.io.fd.File.open(__file__, pysec.io.fd.FO_READ) as ftest:
    test_cnt = ftest.lines(start=32, stop=256, eol='\n', keep_eol=True)
    if ''.join(test_cnt) != ''.join(test_data)[32:256]:
      sys.stdout.write("FAILED with different start and stop\n")
      return
  sys.stdout.write("PASSED\n")
  
if __name__ == '__main__':
  main()
```

```
```

```
```


