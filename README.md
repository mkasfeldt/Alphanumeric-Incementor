Alphanumeric-Incementor
=======================
Test

simple function to increment a alpha-numeric key to the next value
note value follows: 0 < A < a therefor 9 is less than P and Z is less than b
:param value: The value passed to the function
:type value: String
:param onlycaps: Use only capital letters, defaults to True
:type onlycaps: Boolean
:param increment: Number of increments to add, defaults to 1
:type increment: Integer
:param strlen: length of the value
:type maxlen: Integer
:return: the incremented value
:rtype: String
values that should pass

>>> anIncrement('0000000000') 
'0000000001'
>>> anIncrement('0000000009') 
'000000000A'
>>> anIncrement('000000000Z') 
'0000000010'
>>> anIncrement('000000000Z',onlycaps=False) 
'000000000a'
>>> anIncrement('000000000z',onlycaps=False) 
'0000000010'
>>> anIncrement('00000000z',strlen=9,onlycaps=False)
'000000010'

values that should raise exceptions

>>> anIncrement('zzzzzzzzzz',onlycaps=False)
Traceback (most recent call last):
  ...
RuntimeError: incremented value greater than the maximum permitted value
>>> anIncrement('ZZZZZZZZZZ')
Traceback (most recent call last):
	...
RuntimeError: incremented value greater than the maximum permitted value
>>> anIncrement('000000000')
Traceback (most recent call last):
	...
ValueError: input value not equal to required string length:10
>>> anIncrement('000000000a')
Traceback (most recent call last):
	...
ValueError: input value has non-numeric or non-capitalized-letter characters
>>> anIncrement('000000000!',onlycaps=False)
Traceback (most recent call last):
	...
ValueError: input value has non-numeric or non-letter characters
>>> anIncrement('00000000a!',onlycaps=False)
Traceback (most recent call last):
	...
ValueError: input value has non-numeric or non-letter characters
