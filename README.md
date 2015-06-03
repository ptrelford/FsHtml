# FsHtml
F# based HTML DSL

## Building

* Appveyor: [![Build status](https://ci.appveyor.com/api/projects/status/vfuq7shh3piim4d3/branch/master?svg=true)](https://ci.appveyor.com/project/ptrelford/fshtml)
* Travis: [![Build Status](https://travis-ci.org/ptrelford/FsHtml.png?branch=master)](https://travis-ci.org/ptrelford/FsHtml/)

## Example

    let timesTable n =
     html [
      head [title %(sprintf "%d Times table" n)]
      body [
       ul [for i in 1..12 ->
            li %(sprintf "%d x %d = %d" n i (n*i)) ]
      ]
     ]
     |> Html.toString
  
     let page = timesTable 3
