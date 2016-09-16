#Elixir in 15 minutes
  This guide will show you in 15 minutes how powerfull Elixir language is. Feel free to send me a PR.
  
  Shall we begin?
  
### Index
1. Basic Data types
2. Operators
3. Pattern Matching
4. Control-Flow Structures
5. Functions

### Basic Data types
```elixir
1 #integer
0xA #integer
2.0 #float
"abcd" #string
<<101, 108, 105, 120, 105, 114>> #bitstring "elixir"
'elixir' #char list
[1, 2 ,3] #list
[a: 1, b: 2] #keyword list
{1,2,3} #tuple
%{a: 2, b: 3} #map
true #booleans are just atoms
is_boolean(:false) # -> true 
is_atom(nil) # -> true
is_nil(:nil) # -> true
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
 #In elixir = is our match operator.
 x = 10
 10 = x #Same value. No problem
 12 = x
 ** (MatchError) no match of right hand side value: 10
 #All values will match
 [a, b, c] = [1, 2, 3]
 [a, b, c] = [1, 2]
 ** (MatchError) no match of right hand side value: [1, 2]
 {:ok, value} = {:ok, [1, 2, 3]}
 {:error, _} = {:error, "some discarded value"}
 #List head and tail
 [h|t] = [1, 2, 3] #h -> 1, t -> [2, 3]
 <<c, 108>>  = <<101, 108>> #Bitstrings
 #The pin(^) operator. Used when you want to match against a variable's value rather than rebind it
 x = 2
 ^x = 2
 ^x = 3
 ** (MatchError) no match of right hand side value: 3
 {y, ^x} = {2, 2}
 {y, ^x} = {3, 2}
 {y, ^x} = {2, 3}
 ** (MatchError) no match of right hand side value: {2, 3}
```
### Control-Flow Structures
```elixir
 #Comparing a value against many patterns with case
 case {:ok, x} do
   {:error, 10} ->
     IO.puts("will never match")
   _ ->
     IO.puts("always matches")
 end
 #Finding the first condition which evaluates to true(any value except for false or nil)
 x = 1
 cond do
   false ->
     IO.puts("this will never match")
   nil ->
     IO.puts("neither this")
   x ->
     IO.puts("ok")
   true ->
     IO.puts("ok too")
 end
 #if and unless are macros
 #if/else
 if true do
   IO.puts("It's true!")
 else
   IO.puts("not true")
 end
 #do/end
 if true, do: 1 + 2
 if false, do: :this, else: :that
 #unless
 unless is_atom(1) do
   IO.puts("Not an atom")
 end
```
### Functions




