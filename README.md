# Webcv

Webcv is a simple wrapper that can implements displaying images, text, and tables via web browsers.

This project is based on [quart](https://pgjones.gitlab.io/quart/index.html) that requires python 3.7+. For older version of Python, please use [webcv-gevent](https://github.com/wanzysky/webcv-gevent) instead.

## Installation

`pip install webcv`


## Sample Usage

![screenshot](screen_shot.png)

```python

import sys

import numpy as np
from webcv import webcv


webcv.head_show("h1", "Test image show")

image = np.random.randint(0, 256, (256, 256, 3), dtype=np.uint8)

webcv.imshow("image", image)
webcv.imshow("resize using webcv", webcv.resize(image, (512, 512)))

# response in 30 seconds
webcv.waitKey(30000)

webcv.head_show("h1", "Test table show")
webcv.table_show("versions", [
    ["python", "opencv", "webcv"],
    [f"version {'.'.join(str(v) for v in sys.version_info)}", cv.__version__, webcv.__version__],
    ])

webcv.waitKey()
```

## Acknowledgement

The project was inspired by a Megvii tool.

## License

MIT License
