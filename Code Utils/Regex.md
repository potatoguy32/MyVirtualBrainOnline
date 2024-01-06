# Identify any kind of "valid" quantities
This regex is useful to identify "valid"quantity values, even if commas, decimal points or not so formal writing is included
`(?<!\S)(?=.)(0|([1-9](\d*|\d{0,2}(,\d{3})*)))?(\.\d*[1-9])?(?!\S)`

This is an example in python
```python
total_items = 'Mostrando 227 resultados y otros 2,233.23 y/o 777,777 .1  1,1'

matches = [occurence.group() for occurence in re.finditer('(?<!\S)(?=.)(0|([1-9](\d*|\d{0,2}(,\d{3})*)))?(\.\d*[1-9])?(?!\S)', total_items) if len(occurence.group()) > 0]

matches
> ['227', '2,233.23', '777,777', '.1']
```
