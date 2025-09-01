# Tomo Coroutine Library

This is a coroutine library for [Tomo](https://tomo.bruce-hill.com) built on
top of a modified version of [libaco](https://libaco.org).

## Example Usage

```ini
# modules.ini
[coroutines]
version=v1.0
git=https://github.com/bruce-hill/tomo-coroutines
```

```tomo
use coroutines

func main()
    co := Coroutine(func()
        say("I'm in the coroutine!")
        yield()
        say("I'm back in the coroutine!")
    )
    >> co
    say("I'm in the main func")
    >> co.resume()
    say("I'm back in the main func")
    >> co.resume()
    say("I'm back in the main func again")
    >> co.resume()
```
