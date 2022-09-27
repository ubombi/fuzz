# fuzzfaker
Make fuzzing great again using `reflect.MakeFunc`


# TODO:

```go
  type Input struct {
    Name string
    Email string `ff:"-,valid_email"`
    Attributes struct {
      Age int
      Website string
    }
  
  }

  ff := fuzfake.New(Input) // recursively iterate over fields, to collect all basic types (and additional config)

	f.Add(ff.Seed()) // define basic type arguments for each field. Optionally passing actual seed values.

  // Fuzz expects weird set of basic typed arguments, so we need to wrap it.
	f.Fuzz(ff.FuzzFunc(t *testing.T, func(input Input){
    and write our tests with less chore.
  }))


```
