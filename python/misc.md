doc création Python https://www.youtube.com/watch?v=GfH4QL4VqJ0

# Vocabulaire

"with statement" : context manager https://docs.python.org/3/reference/compound_stmts.html#with https://docs.python.org/3/reference/datamodel.html#context-managers

Un context manager est un objet qu'on appelle avec `with`. Il va définir deux méthodes, `__enter__`et `__exit__` pour décrire le code qui doit être exécuté avant et après le bloc dans le `with`

# Tests

Il est souvent utile de rajouter un message d'assertion, exemple de bon code recommandé par https://docs.python-guide.org/writing/reading/

```
from test import unittest

from diamond.metric import Metric


class TestMetric(unittest.TestCase):

    def testgetPathPrefix(self):
        metric = Metric('servers.com.example.www.cpu.total.idle',
                        0,
                        host='com.example.www')

        actual_value = metric.getPathPrefix()
        expected_value = 'servers'

        message = 'Actual %s, expected %s' % (actual_value, expected_value)
        self.assertEqual(actual_value, expected_value, message)
```
source : https://github.com/python-diamond/Diamond/blob/master/src/diamond/test/testmetric.py
