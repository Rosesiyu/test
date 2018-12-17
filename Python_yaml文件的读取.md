```yaml
A:12345
B:22345
C:32345
D:42345
```
```python
import yaml
file = open('test.yaml')
print(yaml.load(file))
>>>A:12345 B:22345 C:32345 D:42345
```
