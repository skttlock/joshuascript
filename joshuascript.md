`import` will bring code into scope a la library import

`inplace` will bring code into the file during compilation, a la templating language.

```joshuascript
def enum ExampleEnum {

}

ExampleEnum.random(); is uh... predefined? always valid?
class Enum has method random() defined i guess?
```



```joshuascript
def prog Main =>
	def class ExampleClass =>
		def var exampleVariable : Number = 20;
	
		def main(String[] args) : [public, static, void] {
			call(printf("Variable: #{exampleVariable}"));
			call(printf("Label: #{exampleVariable.label}"));
			call(printf("Value: #{exampleVariable.value}"));
			call(printf("Attributes: #{exampleVariable.attributes}"));
			call(printf("Address: #{exampleVariable.address}"));
			
		fed 
	fed
fed

start(Main);
```

`instruct` 
`<action> <kind> <label> (<argument>) : [<scope>, <type>, <return> : [<type>] ] = > <block> < fed;`

1. what action
2. what kind of said action
3. what to call this
4. labels of argument(s)
5. define the attributes
	1. instruction scope
	2. instruction type (static, etc)
	3. instruction return label
	4. instruction return 

- examples
	- veriable declaration
		- `def var variableName : Number = 30;`
		- (verbose)
			- `def var variableName() : [public, Number, this:[inherit, Number] ] = > 30 < fed;`

| word_type        | keyword    |     | required? | what                              | meaning                                                    | who cares |
| ---------------- | ---------- | --- | --------- | --------------------------------- | ---------------------------------------------------------- | --------- |
|                  | `instruct` |     | i         |                                   |                                                            |           |
| **action**       | `def`      |     | i         |                                   | begin a definition                                         |           |
| kind             | `var`      |     | y         |                                   | of kind Variable                                           |           |
| label (action)   | -          |     | -         | label                             | -                                                          | -         |
|                  | `(`        |     |           | argument delimiter (open)         | define the argument                                        |           |
| label (argument) | -          |     |           | argument label                    |                                                            |           |
|                  | `)`        |     |           | argument delimiter (close)        |                                                            |           |
|                  | `:`        |     |           | attributes assignment operator    |                                                            |           |
|                  | `[`        |     |           | group/set/array delimiter (open)  | define a group                                             |           |
| scope            | `public`   |     |           | scope constant                    | sets the scope/visibility attribute to public              |           |
|                  | `,`        |     |           |                                   | item separator                                             |           |
| type             | `static`   |     |           |                                   |                                                            |           |
|                  | `,`        |     |           |                                   | seperate items                                             |           |
| label (return)   | -          |     | -         | return label                      |                                                            |           |
|                  | `]`        |     |           | group/set/array delimiter (close) |                                                            |           |
|                  |            |     |           |                                   |                                                            |           |
| **action**       | `fed`      |     | i         |                                   | end current definition                                     |           |
|                  | `;`        |     | yes       |                                   | end of current instruction<br>beginning of new instruction | compiler  |
|                  |            |     |           |                                   |                                                            |           |
|                  |            |     |           |                                   |                                                            |           |
|                  |            |     |           |                                   |                                                            |           |
|                  |            |     |           |                                   |                                                            |           |
| **action**       | call       |     |           |                                   | begin a method call                                        |           |
| **action**       | import     |     |           |                                   |                                                            |           |
| **action**       | inplace    |     |           |                                   |                                                            |           |
|                  |            |     |           |                                   |                                                            |           |
|                  |            |     |           |                                   |                                                            |           |
| kind             | class      |     |           |                                   | of kind Class                                              |           |
| kind             | func       |     |           |                                   | of kind Function                                           |           |
| kind             | enum       |     |           |                                   | of kind Enumeration                                        |           |
| kind             | prog       |     |           |                                   | of kind Program                                            |           |
|                  |            |     |           |                                   |                                                            |           |
|                  |            |     |           |                                   |                                                            |           |
| scope            | priv       |     |           |                                   |                                                            |           |

required? =>
- i = yes, but it is often implied and thus rare
- y = yes
- n = no
- p = preferred

## scratch
#### return label
yes, you will name the return value. this is not require

#### what if 
`=` - assign
`>` - start block
`<` - end block
`|` - end definition
`;` - end instruction

- so its 
	- versus 
		- A)  `def var variableName() : [public, Number, this : [Number] ] = > 30 < fed;`
		- B)  `def var variableName() : [public, Number, this:[Number] ] = > 30 < |;`
	- with ligatures:
		- A)  `def var variableName() : [public, Number, this:[Number] ] => 30 < fed;`
		- B)  `def var variableName() : [public, Number, this:[Number] ] => 30 <|;`
	- without whitespace
		- A)  `defvarvariableName():[public,Number,this:[Number]]=>30<fed;`
		- B)  `defvarvariableName():[public,Number,this:[Number]]=>30<|;`


### misc
`def:<kind>:<label>:{ <block> };` (colon separated?)


