#Elixir in 15 minutes
  This guide will show you in 15 minutes how powerfull Elixir language is. Feel free to send me a PR.
  
  Shall we begin?
### Index
1. Data types
2. Operators
3. Pattern Matching

### Data types
```elixir
1 #integer
0xA #integer
2.0 #float
"abcd" #string
[1, 2 ,3] #list
[a: 1, b: 2] #keyword list
{1,2,3} #tuple
%{a: 2, b: 3} #map
true #boolean
:false #booleans are just atoms
#structs
defmodule Bastard do
  #Default values
  defstruct name: "Jon Snow"
end
jon = %Bastard{name: "Jon Snow"}
ramsay = %{jon | name: "Ramsay Bolton"}
#Structs are bare maps underneath
is_map(jon) #true
```
### Operators
```elixir
 +, -, *, / #Basic arithmetic
 3/2 #returns 1.5
 div(3,2) #Integer division
 rem(3,2) #Remainder
 [1,2] ++ [3,4] #[1,2,3,4]
 [1,2,3,4] -- [3,4] #[1,2]
 #String concatenation
 "ab" <> "cd" #"abcd"
 #Boolean operators and, or and not
 true and :true #true
 #Providing a non-boolean will raise an exception
 1 and true #** (ArgumentError) argument error: 1
 ||, && and ! #All values except nil and false will evaluate to true
 ==, !=, ===, !==, <=, >=, < and > #Comparison operators
 1 == 1.0 #true
 1 === 1.0 #false
 #Sorting order
 number < atom < reference < functions < port < pid < tuple < maps < list < bitstring
```
### Pattern Matching
```elixir
```






