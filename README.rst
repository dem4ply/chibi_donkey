============
Chibi donkey
============

small lib for inflate and compress dict using double underscore
or proccess string using the format double undescore

*********************
how to used with dict
*********************

.. code-block:: python

	import chibi_donkey as donkey

	example = {
		'a': {
			'aa': {
				'aaa': 'aaa',
				'aab': 'aab',
				'aac': 'aac'
			},
			'ab': 'ab',
			'ac': None,
			},
			'b': {
			'ba': [ 1, 2, 3 ],
			'bb': 'bb',
			'bc': None,
			}
	}

	example_compress= {
		'a__aa__aaa': 'aaa',
		'a__aa__aab': 'aab',
		'a__aa__aac': 'aac',
		'a__ab': 'ab',
		'a__ac': None,
		'b__ba': [ 1, 2, 3 ],
		'b__bb': 'bb',
		'b__bc': None,
	}

	assert donkey.compress( example ) == example_compress
	assert donkey.inflate( example_compress ) == example

	assert donkey.get( 'a__aa__aaa', example ) == 'aaa'
	assert donkey.get( 'a__ba', example ) == [ 1, 2, 3 ]

	donkey.setter( 'a__aa__aaa', example, 'asdf' )
	assert donkey.get( 'a__aa__aaa', example ) == 'asdf'


***********************
how to use with strings
***********************


.. code-block:: python

	import chibi_donkey as donkey

	assert donkey.init( 'a__b__c' ) == 'a'
	assert donkey.last( 'a__b__c' ) == 'c'

	assert donkey.key( 'a', 'b', 'c' ) == 'a__b__c'
	assert donkey.partition( 'a__b__c' ) == [ 'a', 'b', 'c' ]
