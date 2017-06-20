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
