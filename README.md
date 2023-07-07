# insfraud’s Code Style Guide (LuaU)

Created 7/7/2023

One of many style guides for Roblox’s version of Lua, LuaU created by insfraud. These practices when writing your code can increase readability and help keep code consistent. 

## Table of Contents
  1. Naming Conventions
  2. Formatting and Indentation
  3. Comments and Documentation
  4. Strings
  5. Classes
  6. Conditional Statements

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
-- Bad
local result: number
```

# Comments and Documentation
_Practices to make your code neatly documented for any other programmers who view you code, and to please your future self._

## Function Documentation
A functions should be neatly documented represented by: --[[ --]]. Documentation should have around a length of 8 lines but are not limited to no more than 14. Docs must give a brief description on how the function operates, what it returns, and the arguments

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

