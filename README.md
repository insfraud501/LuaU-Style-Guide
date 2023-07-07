# insfraud’s Code Style Guide (LuaU)

Created 7/7/2023

One of many style guides for Roblox’s version of Lua, LuaU created by insfraud. These practices when writing your code can increase readability and help keep code consistent. 

## Table of Contents
  [1. Naming Conventions](https://github.com/insfraud501/LuaU-Style-Guide#naming-conventions)
  [2. Formatting and Indentation](https://github.com/insfraud501/LuaU-Style-Guide#formatting-and-indentation)
  [3. Comments and Documentation](https://github.com/insfraud501/LuaU-Style-Guide#comments-and-documentation)
  [4. Strings](https://github.com/insfraud501/LuaU-Style-Guide#strings)
  [5. Classes](https://github.com/insfraud501/LuaU-Style-Guide#classes)
  [6. Conditional Statements](https://github.com/insfraud501/LuaU-Style-Guide#conditional-statements)

# Naming Conventions
_Practices to follow when naming different variables and functions_

## Variable Naming
All variables should be named and styled using camelCase.
```lua
-- Good
local myVariable = "Hi"
local helloWorld = "Hello World!"

-- Bad
local MyVariable = "Hi"
local hello_world = "Hello World!"
```
## Constant Naming
All constants should be fully capitalized. Spaces should be replaced by underscores.
```lua
-- Good
local MY_CONSTANT = "Hi"
local HELLO_WORLD = "Hello World!"

-- Bad
local HelloWorld = "Hello World!"
local hello_earth = "Hii"
```
## Function Naming
All function names should be syled using PascalCase.
```lua
-- Good
local function MyRobloxFunction( myArgument : string )

-- Bad
local function myRobloxFunction( MyArgument : string )
```
## Function Parameter Naming
All parameters for functions should be styled by camelCase
```lua
-- Good
local function MyRobloxFunction( myArgument : string )
```

# Formatting and Indentation

## Curly Braces
After the beginning of a curly brace and before the end of a curly brace a whitespace should be present. For example:
```lua
-- Should Be
local table = { 1, 2, 3, 4, }

-- NOT
local table = {1, 2, 3, 4,}
```

## Commas
With anything that holds elements or objects seperated by a comma such as a table, should have a whilespace present after the comma. For example:
```lua
-- Yes
local table = { 1, 2, 3, 4, 5, }

-- No
local table = {1,2,3,4,5}
```

Moreover, after the last element of a data structure or anything that has objects seperated by commas; a comma should be present, following a whitespace. An example that might help is:
```lua
-- Good
local table = { 1, 2, 3, 4, 5, }

-- Bad
local table = { 1, 2, 3, 4, 5 }
```
Notice the comma after '5', with a whitespace after.

## Parentheses
Relating back to curly braces, after the opening bracket and before the closing bracket, a space must be present. E.g:
```lua
-- Good
local function myFunction( arg1 : string, arg2 : number )

-- Bad
local function myFunction(arg1 : string, arg2: number)
```

## Colons/Type Hints
Before and after a colon, a space must be included. For example:
```lua
-- Good
local result : number
function shop:Init( config : string )

-- Bad
local result: number
function shop:Init( config: string )
```

# Comments and Documentation
_Practices to make your code neatly documented for any other programmers who view you code, and to please your future self._

## Function Documentation
A function should be neatly documented represented by: --[[ --]]: (Beginning : --[[, Closing : --]]. Documentation should have around a length of 8 lines but are limited to no more than 14. Docs must give a brief description on how the function operates, what it returns, and the arguments

The order would go like this.
Firstly: Brief description; what does the function do?
Secondly: Talk about the arguments; what does it do with them?
Finally: State what it returns.

An small example would be this function which gives the player cash:
```lua
--[[
    Adds a number value to the players cash balance ( player.Cash.Balance )
    Specifically, adds the 'cashAmount' argument to their balance.
    Returns the updated cash balance.
--]]
function player.Cash:GiveCash( cashAmount : number )
    self.Balance += cashAmount
    return self.Balance
end
```
## Comment Style
Comments which span more than 1 line must be created by starting with --[[ and ending with --]] on a new line. 
Comments which have a length of one line are recommended to be styled using --//, however it is optional.

```lua
-- Good usage of: --[[ --]]

--[[
    This is a code comment because it would span more than one line.
    The second line of the code comment is right here, hello!
    Finishing off the comment block, bye.
--]]

-- Good Usage of: --//

--// Services...
--// Modules...
```
# Strings

## Apostrophe (') 
Apostrophes are discourgaed when creating string longer than one character. A string that holds only one character must be surrounded by apostrophes.

```lua
-- Good
local character = 'a'

-- Bad
local character = "a"
```

## Quotation Marks (")
Quotation marks must be used to enclose strings longer than one character.
```lua
-- Good
local string = "Hello My Name is Lua!"

-- Bad
local string = 'Hello My Name is Lua!'
local char = "A"
```

## Multi-line and Long Strings
Strings that exceed around 30 characters and span multiple lines, must be concated with eachother and a newline must be present after. An example of a string which spans accross multiple lines:

```lua
local myString = "Lorem ipsum dolor sit amet, consectetur adipiscing elit."..
      "Suspendisse vehicula blandit commodo. Aenean a mi placerat nisi"..
      "ultricies tristique vitae vel nunc. Praesent massa erat, bibendum sit"..
      "amet massa ac, eleifend sollicitudin dolor. Maecenas fermentum elementum lorem"
```

# Classes
_Eseential practices to use when creating classes for better ease of access and readability_

## Essential Functions to Include
All classes **must** include either a method/function named: new, init, or initalize when creating a class. For example:
```lua
-- Instead of doing this:
local car = Car("Mustang")

-- Do this:
local car = Car.new("Mustang")
```

This logic also applies to init/initalize
```lua
-- Also acceptable:
local shop = Shop:Init("Cotton Candy")
local computer = Computer:Initalize("Fast")
```

# Conditional Statements

## nil Checking
Instead of checking if a variable is equal to nil, checking "if variable then" is encouraged instead. For example:
```lua
-- Good
local money = nil
if money then
  print(money)
end

-- Bad
local money = nil
if money ~= nil then
  print(money)
end
```

## Early Returns
Early returns aren't discouraged but should only happen if a variable already or doesn't meet something such as if it isn't initliazed and failsafes fail. Early returns
must either return a warn, error, false, string, or nil value to indicate a fail, or a string, true, value to indicate a success.

```lua
function player:SubtractCash() 
  local money = player:GetCash() -- nil value
  if not money then
    return error("Couldn't get player cash")
  end
```


# Creating

## Creating Variables
1. All variables **must** be created using the 'local' keyword.
```lua
-- Good
local myVar = 1

-- Bad
myVar = 1
```
2. Any variable which is to be initalized without a value, must be initalized to a nil value.
```lua
-- Good
local var = nil

-- Bad
local var
```
- Initalizing a variable to nil comes with exception that you are currently using it such as:
```lua
local money = player:GetCash()
```

## Creating Functions
1. All functions should be created using the 'local' keyword. 
```lua
-- Good
local function myLocalFunction()
```

2. If a function is used in a module it should be created using this format:
```lua
-- Good
function module/tableName (. or :) functionName( arguments... )
    function module.functionName( argument )
    function module:functionName( argument )
```

