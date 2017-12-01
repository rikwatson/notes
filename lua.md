# Lua

.. is a simple programming language liked by people such as [The Tao of Mac](http://taoofmac.com/space/dev/Lua).

Embed in [C#](./csharp) via [nlua.org](http://nlua.org/)

Cool dev. tool [http://twolivesleft.com/Codea/](Here).

Install via, `brew install lua`.

[Learn Lua from JavaScript](https://www.oreilly.com/learning/learn-lua-from-javascript-part-1-an-introduction-to-lua)

 * Lua for programmers:
   * [Part 4: Tips and Tricks](http://nova-fusion.com/2012/09/09/lua-for-programmers-part-4/)
 * [Lua for Python Programmer](http://the4thwiki.com/lua/)

 [Syntax](https://www.lua.org/manual/5.3/manual.html#9)

 TODO: Let's write [Lua](https://github.com/lua/lua) in Go.

 [Lua Parser](http://the-ravi-programming-language.readthedocs.io/en/latest/lua-parser.html)

 * [Docker with Lua](https://hub.docker.com/r/dexec/lua/~/dockerfile/)

## Compile Online

 * [API](https://luac.mtasa.com/api/)

Need to embed `luac` into something or other. i.e. a Lua bytecode compiler.

## Reading The Code

Recommended reading order:

[Online Lua 5.1 source code browser](http://www.lua.org/source/5.1/)

 * `lmathlib.c`, `lstrlib.c`: get familiar with the external C API. Don't bother with the pattern matcher though. Just the easy functions.
 * `lapi.c`: Check how the API is implemented internally. Only skim this to get a feeling for the code. Cross-reference to lua.h and luaconf.h as needed.
 * `lobject.h`: tagged values and object representation. skim through this first. you'll want to keep a window with this file open all the time.
 * `lstate.h`: state objects. ditto.
 * `lopcodes.h`: bytecode instruction format and opcode definitions. easy.
 * `lvm.c`: scroll down to `luaV_execute`, the main interpreter loop. see how all of the instructions are implemented. skip the details for now. reread later.
 * `ldo.c`: calls, stacks, exceptions, coroutines. tough read.
 * `lstring.c`: string interning. cute, huh?
 * `ltable.c`: hash tables and arrays. tricky code.
 * `ltm.c`: metamethod handling, reread all of lvm.c now.
 * You may want to reread `lapi.c` now.
 * `ldebug.c`: surprise waiting for you. abstract interpretation is used to find object names for tracebacks. does bytecode verification, too.
 * `lparser.c`, `lcode.c`: recursive descent parser, targetting a register-based VM. start from chunk() and work your way through. read the expression parser and the code generator parts last.
 * `lgc.c`: incremental garbage collector. take your time.
 * Read all the other files as you see references to them. Don't let your stack get too deep though.

If you're done before X-Mas and understood all of it, you're good. The information density of the code is rather high.

[Annotated Source](http://stevedonovan.github.io/lua-5.1.4/)

 * https://github.com/Shopify/go-lua
 * https://github.com/yuin/gopher-lua
 * https://otm.github.io/2015/07/embedding-lua-in-go/

 ----



Cool dev. tool [http://twolivesleft.com/Codea/](Here).

# Moonshine

[Moonshine](http://moonshinejs.org/) is a lightweight JavaScript VM for compiled LUA byte code.

To try Moonshine

# Install some stuff

```bash
brew install lua
brew install node
npm install -g moonshine
```

# Create a Hello Word Program in Lua

## hello.lua

```lua
print 'Hello, World.'
```

Use [Moonshine](http://moonshinejs.org/) to compile `hello.lua` to bytecode (Called distilling)

```bash
moonshine distil hello.lua
File created: hello.lua.json
```

[Download](http://moonshinejs.org/download) Moonshine VM

# Load bytecode (JSON) into static web-site

```html
<html>
	<head>
		<script src="./js/moonshine.js"></script>
		<script>
			var vm = new shine.VM();
			vm.load('./lua/hello.lua.json');
		</script>
	</head>
	<body>
	⋮
	</body>
</html>
```

# A more complex example

## light-seconds.lua

```lua
local lightSeconds = distanceToMoon / speedOfLight
log('It takes '..lightSeconds..' seconds for light to travel from the Moon.')
```

## index.html (Partial)

```html
<script src="./js/moonshine.js"></script>
<script>
        var vm, env;

        env = {
                speedOfLight: 299792458,
                distanceToMoon: 384400000,
                log: function log (message) {
                        console.log('Message from Lua: ' + message);
                }
        };

        vm = new shine.VM(env);
        vm.load('./lua/light-seconds.lua.json');
</script>
```


# Objects

From [eev.ee](https://eev.ee/blog/2017/11/28/object-models/)

Lua doesn’t have an object model. Instead, it gives you a handful of very small primitives for building your own object model. This is pretty typical of Lua — it’s a very powerful language, but has been carefully constructed to be very small at the same time. I’ve never encountered anything else quite like it, and “but it starts indexing at 1!” really doesn’t do it justice.

The best way to demonstrate how objects work in Lua is to build some from scratch. We need two key features. The first is **metatables**, which bear a passing resemblance to Python’s metaclasses.

## Tables and metatables

The table is Lua’s mapping type and its primary data structure. Keys can be any value other than nil. Lists are implemented as tables whose keys are consecutive integers starting from 1. Nothing terribly surprising. The dot operator is sugar for indexing with a string key.

```lua
local t = { a = 1, b = 2 }
print(t['a'])  -- 1
print(t.b)  -- 2
t.c = 3
print(t['c'])  -- 3
```

A metatable is a table that can be associated with another value (usually another table) to change its behavior. For example, operator overloading is implemented by assigning a function to a special key in a metatable.

```lua
local t = { a = 1, b = 2 }
--print(t + 0)  -- error: attempt to perform arithmetic on a table value

local mt = {
    __add = function(left, right)
        return 12
    end,
}
setmetatable(t, mt)
print(t + 0)  -- 12
```

Now, the interesting part: one of the special keys is `__index`, which is consulted when the base table is indexed by a key it doesn’t contain. Here’s a table that claims every key maps to itself.

```lua
local t = {}
local mt = {
    __index = function(table, key)
        return key
    end,
}
setmetatable(t, mt)
print(t.foo)  -- foo
print(t.bar)  -- bar
print(t[3])  -- 3
```

`__index` doesn’t have to be a function, either. It can be yet another table, in which case that table is simply indexed with the key. If the key still doesn’t exist and that table has a metatable with an `__index`, the process repeats.

With this, it’s easy to have several unrelated tables that act as a single table. Call the base table an object, fill the `__index` table with functions and call it a class, and you have half of an object system. You can even get prototypical inheritance by chaining `__index`es together.

At this point things are a little confusing, since we have at least three tables going on, so here’s a diagram. Keep in mind that Lua doesn’t actually have anything called an “object”, “class”, or “method” — those are just convenient nicknames for a particular structure we might build with Lua’s primitives.

```
                    ╔═══════════╗        ...
                    ║ metatable ║         ║
                    ╟───────────╢   ┌─────╨───────────────────────┐
                    ║ __index   ╫───┤ lookup table ("superclass") │
                    ╚═══╦═══════╝   ├─────────────────────────────┤
  ╔═══════════╗         ║           │ some other method           ┼─── function() ... end
  ║ metatable ║         ║           └─────────────────────────────┘
  ╟───────────╢   ┌─────╨──────────────────┐
  ║ __index   ╫───┤ lookup table ("class") │
  ╚═══╦═══════╝   ├────────────────────────┤
      ║           │ some method            ┼─── function() ... end
      ║           └────────────────────────┘
┌─────╨─────────────────┐
│ base table ("object") │
└───────────────────────┘
```

Note that a metatable is not the same as a class; it defines behavior, not methods. Conversely, if you try to use a class directly as a metatable, it will probably not do much. (This is pretty different from e.g. Python, where operator overloads are just methods with funny names. One nice thing about the Lua approach is that you can keep interface-like functionality separate from methods, and avoid clogging up arbitrary objects’ namespaces. You could even use a dummy table as a key and completely avoid name collisions.)

Anyway, code!

```lus
local class = {
    foo = function(a)
        print("foo got", a)
    end,
}
local mt = { __index = class }
-- setmetatable returns its first argument, so this is nice shorthand
local obj1 = setmetatable({}, mt)
local obj2 = setmetatable({}, mt)
obj1.foo(7)  -- foo got 7
obj2.foo(9)  -- foo got 9
```

Wait, wait, hang on. Didn’t I call these methods? How do they get at the object? Maybe Lua has a magical this variable?

Methods, sort of

Not quite, but this is where the other key feature comes in: method-call syntax. It’s the lightest touch of sugar, just enough to have method invocation.

```lua
-- note the colon!
a:b(c, d, ...)

-- exactly equivalent to this
-- (except that `a` is only evaluated once)
a.b(a, c, d, ...)

-- which of course is really this
a["b"](a, c, d, ...)
```

Now we can write methods that actually do something.

```lua
local class = {
    bar = function(self)
        print("our score is", self.score)
    end,
}
local mt = { __index = class }
local obj1 = setmetatable({ score = 13 }, mt)
local obj2 = setmetatable({ score = 25 }, mt)
obj1:bar()  -- our score is 13
obj2:bar()  -- our score is 25
```

And that’s all you need. Much like Python, methods and data live in the same namespace, and Lua doesn’t care whether obj:method() finds a function on obj or gets one from the metatable’s `__index`. Unlike Python, the function will be passed self either way, because self comes from the use of `:` rather than from the lookup behavior.

(Aside: strictly speaking, any Lua value can have a metatable — and if you try to index a non-table, Lua will always consult the metatable’s `__index`. Strings all have the string library as a metatable, so you can call methods on them: try `("%s %s"):format(1, 2)`. Numbers, strings, functions, and nil each share a type-specific metatable, and you can only change it with the `debug` library which is often unavailable, so this is of limited use. But if you’re writing Lua bindings from C, you can give your pointers metatables directly to give them methods implemented in C.)

Bringing it all together

Of course, writing all this stuff every time is a little tedious and error-prone, so instead you might want to wrap it all up inside a little function. No problem.


```lua
local function make_object(body)
    -- create a metatable
    local mt = { __index = body }
    -- create a base table to serve as the object itself
    local obj = setmetatable({}, mt)
    -- and, done
    return obj
end

local Dog = {
    -- this acts as a "default" value; if obj.barks is missing, __index will
    -- kick in and find this value on the class.  but if obj.barks is assigned
    -- to, it'll go in the object and shadow the value here.
    barks = 0,

    bark = function(self)
        self.barks = self.barks + 1
        print("woof!")
    end,
}

local mydog = make_object(Dog)
mydog:bark()  -- woof!
mydog:bark()  -- woof!
mydog:bark()  -- woof!
print(mydog.barks)  -- 3
print(Dog.barks)  -- 0
```

It works, but it’s fairly barebones. The nice thing is that you can extend it pretty much however you want. I won’t reproduce an entire serious object system here — lord knows there are enough of them floating around — but the implementation I have for my LÖVE games lets me do this:

```lua
local Animal = Object:extend{
    cries = 0,
}

-- called automatically by Object
function Animal:init()
    print("whoops i couldn't think of anything interesting to put here")
end

-- this is just nice syntax for adding a first argument called 'self', then
-- assigning this function to Animal.cry
function Animal:cry()
    self.cries = self.cries + 1
end

local Cat = Animal:extend{}

function Cat:cry()
    print("meow!")
    Cat.__super.cry(self)
end

local cat = Cat()
cat:cry()  -- meow!
cat:cry()  -- meow!
print(cat.cries)  -- 2
```

When I say you can extend it however you want, I mean that. I could’ve implemented Python (2)-style `super(Cat, self):cry()` syntax; I just never got around to it. I could even make it work with multiple inheritance if I really wanted to — or I could go the complete opposite direction and only implement composition. I could implement descriptors, customizing the behavior of individual table keys. I could add pretty decent syntax for composition/proxying. I am trying very hard to end this section now.

## The Lua philosophy

Lua’s philosophy is to… not have a philosophy? It gives you the bare minimum to make objects work, and you can do absolutely whatever you want from there. Lua does have something resembling prototypical inheritance, but it’s not so much a first-class feature as an emergent property of some very simple tools. And since you can make __index be a function, you could avoid the prototypical behavior and do something different entirely.

The very severe downside, of course, is that you have to find or build your own object system — which can get pretty confusing very quickly, what with the multiple small moving parts. Third-party code may also have its own object system with subtly different behavior. (Though, in my experience, third-party code tries very hard to avoid needing an object system at all.)

It’s hard to say what the Lua “culture” is like, since Lua is an embedded language that’s often a little different in each environment. I imagine it has a thousand millicultures, instead. I can say that the tedium of building my own object model has led me into something very “traditional”, with prototypical inheritance and whatnot. It’s partly what I’m used to, but it’s also just really dang easy to get working.

Likewise, while I love properties in Python and use them all the dang time, I’ve yet to use a single one in Lua. They wouldn’t be particularly hard to add to my object model, but having to add them myself (or shop around for an object model with them and also port all my code to use it) adds a huge amount of friction. I’ve thought about designing an interesting ECS with custom object behavior, too, but… is it really worth the effort? For all the power and flexibility Lua offers, the cost is that by the time I have something working at all, I’m too exhausted to actually use any of it.