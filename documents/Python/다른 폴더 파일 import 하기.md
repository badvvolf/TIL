# 다른 폴더 파일 import 하기

## 하위 폴더
* from 경로.파일 import xx

## 상위, 형제 폴더
* 경로를 추가해야 한다. 
```python
import sys
sys.path.insert(0, '경로')
from 경로.파일 import XX
```