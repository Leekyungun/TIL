# file



## 동시에 접근하였을때 에러나지않는 방법

```python
import json
import time


def get_data(before_data):
    data = None

    with open('data.txt', 'r') as f:
        _data = f.read()
        if _data:
            data = json.loads(_data)
        else:
            data = before_data
    return data


if __name__ == '__main__':
    before_data = None
    while True:
        time.sleep(0.1)
        data = get_data(before_data)
        before_data = data
        print(data)

```

