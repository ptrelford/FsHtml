# FsHtml
Simple F# DSL for generating statically generating HTML programmatically.

## Building

* Appveyor: [![Build status](https://ci.appveyor.com/api/projects/status/vfuq7shh3piim4d3/branch/master?svg=true)](https://ci.appveyor.com/project/ptrelford/fshtml)
* Travis: [![Build Status](https://travis-ci.org/ptrelford/FsHtml.png?branch=master)](https://travis-ci.org/ptrelford/FsHtml/)

## Example

```F#
let timesTable n =
 html [
  head [title %(sprintf "%d Times table" n)]
  body [
   ul [for i in 1..12 ->
        li %(sprintf "%d x %d = %d" n i (n*i)) ]
  ]
 ]

let page = timesTable 3 |> Html.toString
```
Outputs:
```HTML
<html>
 <head>
  <title>3 Times table</title>
 </head>
 <body>
  <ul>
   <li>3 x 1 = 3</li>
   <li>3 x 2 = 6</li>
   <li>3 x 3 = 9</li>
   <li>3 x 4 = 12</li>
   <li>3 x 5 = 15</li>
   <li>3 x 6 = 18</li>
   <li>3 x 7 = 21</li>
   <li>3 x 8 = 24</li>
   <li>3 x 9 = 27</li>
   <li>3 x 10 = 30</li>
   <li>3 x 11 = 33</li>
   <li>3 x 12 = 36</li>
  </ul>
 </body>
</html>
```
