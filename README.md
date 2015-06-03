# FsHtml
F# based HTML DSL

## Building

* Windows: [![Build status](https://ci.appveyor.com/api/projects/status/vfuq7shh3piim4d3/branch/master?svg=true)](https://ci.appveyor.com/project/ptrelford/fshtml)

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
