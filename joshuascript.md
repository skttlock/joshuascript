`import` will bring code into scope a la library import

`inplace` will bring code into the file during compilation, a la templating
language.

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
		def var privateVar : private

		def main(String[] args) : [public, static, void] {
			call(printf("Variable: #{exampleVariable}"));
			call(printf("Label: #{exampleVariable.label}"));
			call(printf("Value: #{exampleVariable.value}"));
			call(printf("Attributes: #{exampleVariable.attributes}"));
			call(printf("Address: #{exampleVariable.address}"));
			console.lineOut => call().instructionCount <;
			lineOut = call().instructionCount;
			dest = console.address;
			log(dest);
		fed
	fed
fed

start(Main);
```

`instruct`
`<action> <kind> <label> (<argument>) : [<context>, <type>, <return> : [<type>] ] = > < fed;`

0. (this is an instruction)
1. what action
2. what kind of said action
3. what to call this
4. labels of argument(s)
5. attributes assignment operator
   1. instruction context (scope label or address of a block)
   2. instruction type (static, etc)
   3. instruction return label
   4. instruction return

- examples
  - veriable declaration
    - (non-verbose)
      - `def var variableName : Number = 30;`
    - (verbose)
      - `def var variableName() : [public, Number, this:[inherit, Number] ] = > 30 < fed;`

### Keywords

| word_type                  | keyword    | rq? | what                              | meaning                                                     |
| -------------------------- | ---------- | --- | --------------------------------- | ----------------------------------------------------------- |
|                            | `instruct` | i   |                                   |                                                             |
| **action**                 | `def`      | i   |                                   | begin a definition                                          |
| kind                       | `var`      | y   |                                   | of kind Variable                                            |
| label (action)             | -          | -   | label                             | -                                                           |
|                            | `(`        |     | argument delimiter (open)         | define the argument                                         |
| label (argument)           | -          |     | argument label                    |                                                             |
|                            | `)`        |     | argument delimiter (close)        |                                                             |
|                            | `:`        |     | attributes assignment operator    |                                                             |
|                            | `[`        |     | group/set/array delimiter (open)  | define a group                                              |
| context                    | `public`   |     | scope constant                    | sets the scope of this to the public context                |
|                            | `,`        |     |                                   | item separator                                              |
| type                       | `static`   |     |                                   |                                                             |
|                            | `,`        |     |                                   | seperate items                                              |
| label (return)             | -          | -   | return label                      |                                                             |
|                            | `]`        |     | group/set/array delimiter (close) |                                                             |
| **action**                 | `fed`      | i   |                                   | end current definition                                      |
| action                     | `;`        | yes |                                   | end current instruction<br>(= beginning of new instruction) |
| **action**                 | `call`     |     |                                   | begin a method call                                         |
| **action**                 | `import`   |     |                                   |                                                             |
| **action**                 | `inplace`  |     |                                   |                                                             |
| kind                       | `class`    |     |                                   | of kind Class                                               |
| kind                       | `func`     |     |                                   | of kind Function                                            |
| kind                       | `enum`     |     |                                   | of kind Enumeration                                         |
| kind                       | `prog`     |     |                                   | of kind Program                                             |
| kind                       | `script`   |     |                                   | of kind Script                                              |
|                            | `instruct` |     |                                   | define an instruction                                       |
| constant (label, function) | `log()`    |     |                                   |                                                             |
| constant (label, variable) | `lineOut`  |     |                                   | buffer where text gets stored before it is printed          |
| constant(label, variable)  | `console`  |     |                                   |                                                             |
| constant(label, scope)     | `priv`     |     |                                   |                                                             |

###### Table Key (by column)

- "rq?" == required? =>
  - i = yes, but it is often implied and thus rare
  - y = yes
  - n = no
  - p = preferred

### Predefined labels

### scratch

#### return label

yes, you will name the return value. this is not require

#### what if

`=` - assign `>` - start block `<` - end block `|` - end definition `;` - end
instruction

- so it's between:
  - A)
    `def var variableName() : [public, Number, this : [Number] ] = > 30 < fed;`
  - B) `def var variableName() : [public, Number, this:[Number] ] = > 30 < |;`
  - with ligatures:
    - A)
      `def var variableName() : [public, Number, this:[Number] ] => 30 < fed;`
    - B) `def var variableName() : [public, Number, this:[Number] ] => 30 <|;`
  - without whitespace
    - A) `defvarvariableName():[public,Number,this:[Number]]=>30<fed;`
    - B) `defvarvariableName():[public,Number,this:[Number]]=>30<|;`

### misc

`def:<kind>:<label>:{ <block> };` (colon separated?)

##### keyword ideas

### 
