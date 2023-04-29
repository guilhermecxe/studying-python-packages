# Estilos
Existem diferentes estilos de documentação. Alguns deles são:

## Estilo do Google
```python
"""Summary line.

Extended description of function.

Args:
    arg1 (int): Description of arg1
    arg2 (str): Description of arg2

Returns:
    list: a list of strings representing the header columns
"""
```

## Estilo do NumPy
```py
"""Gets and prints the spreadsheet's header columns

Parameters
----------
file_loc : str
    The file location of the spreadsheet
print_cols : bool, optional
    A flag used to print the columns to the console (default is False)

Returns
-------
list
    a list of strings representing the header columns
"""
```

### Descrevendo parâmentros

Quando o parêmetro aceita array ou objetos que podem ser convertidos para array:
```py
"""
a: array_like
    Input array or object...
"""
```

Quando o parâmetro aceita diferentes tipos ou diferentes valores:
```py
"""
axis : {int, tuple of int, None}
...
interpolation : {'linear', 'lower', 'higher', 'midpoint', 'nearest'}
"""
```

### Descrevendo retornos
(Utilizando o estilo NumPy)

```python
"""
Returns
-------
percentile : scalar or ndarray
    If `q` is a single percentile and `axis=None`, then the result
    is a scalar. If multiple percentiles are given, first axis of
    the result corresponds to the percentiles...
"""
```

### Outras seções

Além de `Parameters` e `Returns`, outras seções que podem estar presentes são:

- `Raises`
- `See Also`
- `Notes`
- `References`
- `Examples`

## Estilo reStructuredText
```py
"""Gets and prints the spreadsheet's header columns

:param file_loc: The file location of the spreadsheet
:type file_loc: str
:param print_cols: A flag used to print the columns to the console
    (default is False)
:type print_cols: bool
:returns: a list of strings representing the header columns
:rtype: list
"""
```