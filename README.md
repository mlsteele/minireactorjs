# MiniReactor
Minimal reactive programming base for javascript (coffeescript).

```bash
coffee minireactor.coffee
```

```coffee
# create a new reactive context
ctx = new MiniReactor()

# store initial values for 'frobnitz' and 'dingle-arm'
ctx.set 'frobnitz', 2
ctx.set 'dingle-arm', true

# teach it how to render 'frobnitz'
# this will happen once right now
# this will also happen whenever the value of 'frobnitz' is changed
ctx.autorun ->
  console.log "frobnitz is set to #{ctx.get 'frobnitz'}"

# teach it how to render 'dingle-arm'
ctx.autorun ->
  if ctx.get 'dingle-arm'
    console.log "watch out for the dingle-arm"
  else
    console.log "dingle-arm disengaged"

# set some new values for 'frobnitz' and 'dingle-arm'
ctx.autorun ->
  ctx.set 'frobnitz', 3
  ctx.set 'dingle-arm', false

# set a new value for 'frobnitz'
# set's do not have to be run inside 'autorun' blocks
ctx.set 'frobnitz', 4
```
