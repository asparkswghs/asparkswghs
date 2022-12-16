# Computer Programming with Python (1) Final Notes

List of topics-- reflect upon and provide an example

### Common output problems with variables
- Outputting requires string conversion
- Variables defined within functions cannot escape scope
- Variables from outside func. must be passed as ar or defined globally
```python
def output():
  number = 5
  return number

numbers = [number, 5]
```
The last line would raise a `NameError` exception because `number` is only defined within the `output` function, and is not within the global scope.

```python
gpa = 3.1415
print(gpa)
```
This would raise a `TypeError` because `print()` takes strings, and `gpa` is a float.

The correct method is below:
```python
gpa = 3.1415
print(string(gpa))
```

### User Input Issues
Always specify what sort of input you want from the user.
for example:
```python
while True: # Continue asking for input until it is correct
  try:
    gpa = float(input("Enter GPA as Decimal: ")) # collect input and convert to float
    break # break from loop
  except TypeError: # Catch TypeError when input is not a float
    print("GPA should be a decimal. Try again.") # Tell user to use a decimal
```

### Mathematical Operators Pitfalls
- Order of Operations (PEMDAS)
- Incorrect parenthesis placement
```python
2 + 3 * 4
```
In the above example, `3 * 4` would happen first, then the `2` would be added.

### Code Comments
- Comments are important to explain how your code works for other contributors to a project
- Making an outline before starting to code
- Todo list / Outline
- Disable code while troubleshooting

#### Types of comments
```python
# Single-line comment. Everything after the # is commented
"""
Multi-line comments can span
as many lines
as you want.
They can use 3 single or double quotes.
"""
```

### Looping
`while` vs. `for` loops

##### `for`
When you know EXACTLY how many times to rerun code in advance
OR when going through objects in a list
```python
for i in range(3):
  do_stuff(foo, bar=baz)
```

##### `while`
When you don't know how many times it should be run, but you _do_ know what criteria must be met to stop it.
```python
while criteria:
  try:
    criteria = try_stuff()
  except AnError:
    criteria = False
```

### Logic: `if`/`elif`/`else`
To query if a statement is true, then run code if it returns `True`
Exempli Gratia:
```python
if nextcord.user.id in db["admins"]: # Is the user in the list?
  await interaction.send("Successful!") # If so, run this!
elif nextcord.user.id in db["mods"]: # If not, try this list!
  await interaction.send("Some Permission...") # If they are here, run this!
else:                                # If they're not in any of the above lists,
  await interaction.send("No Permission.") # run this code!
  logging.debug(cfg["messages"]["noperm"] # and this too.
```

### Functions
Define functions and parameters with `def`
```python
def function(param1, param2): # define function, with required parameters param1 and param2
  value = param1 ** param2    # do things with those parameters
  return value                # return the result for use by others
print(function(2,5))          # Now, do something with the function! (will return 32)
```

### Tkinter
Graphical library for python
##### Trouble with Tkinter
- 

##### When should u use console over GUI
- technical users
- server application
- simple text or numbers
- low-power oro embedded
- machine w/o graphics
