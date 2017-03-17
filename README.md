btw-samples-elixir
==================

Community port of the Being the Worst reference samples to Elixir

## Testing mix projects
$ cd <ExerciseFolder>
$ docker-compose run --rm web mix test --cover --trace --listen-on-stdin `#or docker-compose up`

## Testing scripts
ExerciseFolder
├── sample_file.exs
├── sample_files_test.exs

```
# sample_file.exs
defmodule Binaries do
  def printable?(binary) do
    Enum.all? binary, &(&1 >= ?\s && &1 <= ?´)
  end
end
```

```
# sample_file_test.exs
ExUnit.start

defmodule BinariesTest do
  use ExUnit.Case
  test "printable?" do
    assert Binaries.printable?('abc') == true
  end
end
```

```
# running
$ cd <ExerciseFolder>
$ docker-compose run --rm web elixir -r sample_file.exs sample_file_test.exs
```
