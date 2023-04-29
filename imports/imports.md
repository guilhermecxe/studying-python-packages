# Imports

Se eu tenho um pacote chamado `package` e um subpacote dentro dele chamado `subpackage`, só é possível fazer uso de `subpackage` em um script externo se feito como no exemplo abaixo

```py
# script.py
import package
help(package.subpackage)
```

se houver um `import` de `subpackage` no `__init__.py` de `package`. Esse `import` em `package` pode ser feito de modo absoluto:

```py
# package/__init__.py
from package import subpackage
```
ou relativo:
```py
# package/__init__.py
from . import subpackage
```

(O import absoluto é o mais recomendado dentro de `__init__.py`)

Isso porque sem esses `import`'s, `package` "desconhece" a existência de `subpackage`.

Até aqui foi usado um subpacote como exemplo, mas a lógica segue a mesma para módulos dentro do pacote.

## Cheat sheet

- `from . import module`
(Do diretório atual, importar módulo)
- `from .. import module`
(Do diretório logo acima importar módulo)
- `from .module import function`
(Do módulo no diretório atual, importar função)
- `from ..subpackage.module import function`
(Do módulo pertencente a subpacote do diretório acima, importar função)