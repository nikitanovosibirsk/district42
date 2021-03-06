# district42

Data description language (DDL) for defining data models.

### Usage

```python
from district42 import json_schema as schema

BlogPost = schema.object({
  'id':         schema.integer.positive,
  'text':       schema.string.max_length(140),
  'lang':       schema.enum('en', 'fr', 'de', 'es', 'it', 'ru'),
  'author':     schema.object({
                  'id':        schema.string.alpha_num.lowecase,
                  'name':      schema.string.length(3, 16),
                  'image_url': schema.string.uri
                }),
  'created_at': schema.timestamp.iso
})
```

### Installation

```sh
$ pip3 install district42
```

### Tests

```sh
$ python3 setup.py install
$ python3 -m unittest tests
```

### See Also

- [valeera](https://github.com/nikitanovosibirsk/valeera) - Validator for district42 schema
- [blahblah](https://github.com/nikitanovosibirsk/blahblah) - Fake data generator for district42 schema
