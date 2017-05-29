#  The Go Programming Language

## cf

 * [ToM](http://taoofmac.com/space/dev/Golang)
 * [Go By Example](https://gobyexample.com/)
 * [Go Books](https://github.com/dariubs/GoBooks)
 * [How I Start](http://howistart.org/posts/go/1)
 * Talk outlinig Go's [rational](https://talks.golang.org/2012/splash.article)
 * Hackernoon [articles](https://hackernoon.com/tagged/golang)
 * [Effective](https://golang.org/doc/effective_go.html) Go
 * Go [Best Proctices 2016](https://peter.bourgon.org/go-best-practices-2016/)

## Installation

Follow macOS instructions [here](https://golang.org/doc/install).

```
go run main.go
go build system.go
```

Local doc. : `godoc -http=:6060`

`go` & [Heroku](https://devcenter.heroku.com/articles/getting-started-with-go#prepare-the-app)

```
go install github.com/rikwatson/hello
```

The above command will put an executable command named hello (or hello.exe) inside the bin directory of your workspace. Execute the command to see the greeting:

```
$ $GOPATH/bin/hello
hello, world
```

### Environment variables

TODO: Stuff here about `$HOME` etc. [Setting up](https://www.raulmurciano.com/articles/setting-up-go-for-development/) for development.

```
$ echo 'export GOPATH=$HOME' >> $HOME/.profile
$ source $HOME/.profile
$ go env | grep GOPATH
GOPATH="/Users/myusername"
```

## JSON & Go

The ability to decode arbiray JSON is key to a number of apps I'm considerings, here are some resources to read about.

 * From the official Go [blog](http://blog.golang.org/json-and-go)
 * `msheap` [golang: Encode/Decode arbitrary JSON](https://michaelheap.com/golang-encodedecode-arbitrary-json/)
 * `deval.io` [Go: Handling Arbitrary JSON](http://devel.io/2013/08/19/go-handling-arbitrary-json/)
 * StackOverflow [Decode arbitrary JSON in Go](http://stackoverflow.com/questions/30174220/)

## A Music Player in Go

 * [moggio](https://github.com/mjibson/moggio), looks rather cool.
 
## Go App Engine

Download from [here](https://cloud.google.com/appengine/downloads?hl=en#Google_App_Engine_SDK_for_Go), unzip & then:

```bash
export PATH=/path/to/go_appengine:$PATH
```

Also add to `~/.profile` & do a `source ~/.profile`. Shold know have `goapp` etc available.

Then a swift

```bash
cd 
open http://localhost:8080/
goapp serve .
[Cmd-R]
```

and we're in business - edit the `.go` and it will get recompiler on the fly. REPL..

Comming next look [here](https://cloud.google.com/appengine/docs/go/#creating_a_simple_http_handler).

# Using go

 * https://cloud.google.com/appengine/docs/go/
 * https://cloud.google.com/appengine/docs/go/gettingstarted/usingusers

## Google App Engine

 * [AppStats](https://github.com/mjibson/appstats)
 * Go runtime

# Google App Engine / [Google Compute Engine](https://cloud.google.com/compute/)

## [Google App Engine](https://cloud.google.com/appengine/docs/go/)

Hosted App - `go`, `python`, etc

 * Find performance bottlenecks
 * Defer work
 * Betching
 * Caching
 * Concurrency
 * Control variance
 * golang.org/s/turkey-doodle
 * github.com/mjibson/appstats  
   AppStats certainly looks interesting. A `golang` version of the `Python` package. Also worth looking at the source
   code as quite performant & possibly similar to what we may end up needing.
 * appenge / taskqueue -- appengine / delay package 

GetMulti instead of Get, PutMulti instead of Put.

Datastore.Get memcache.Get - cross instance (memcache is not persistant)
Use RAM ! Not shared though.

Concurrent - go golang.

 * [golang.org](golang.org)
 * [developers.google.com/appengin/docs/go](developers.google.com/appengin/docs/go)
 * [golang.org/s/io13-ae-talk](golang.org/s/io13-ae-talk) Talk & gophermart app
 * [gethub.com/mjibson/appstats](gethub.com/mjibson/appstats)
 

`goapp serve .` & `goapp depoy .`

```bash
cd ~/Documents/myapp
goapp serve
# Open http://localhost:8080 in Chrome
```

Also

```bash
cd ~/Downloads/go_wiki
go run simple_web_server.go
``` 

## VM Management

 * At [Apcera](https://www.apcera.com/blog/using-golang-virtual-machine-management)

## Google docs

 * [Spreadsheet](https://developers.google.com/sheets/api/quickstart/go)
 * And in [GitHub](https://github.com/Iwark/spreadsheet)

## Resources

 * `go` using [URL fetch](https://cloud.google.com/appengine/docs/go/urlfetch/) API in GAE.
 * AppStats in Go - [github](https://github.com/mjibson/appstats) 
 * golang, [creating a simple HTTP handler](https://cloud.google.com/appengine/docs/go/#creating_a_simple_http_handler)
 * [Not Another Go/Golang net/http Tutorial](http://soryy.com/blog/2014/not-another-go-net-http-tutorial/)


## Links to investigate

 * https://npf.io/2014/10/why-everyone-hates-go/
 * https://npf.io/2014/05/diffing-go-with-beyond-compare/

## Videos

 * [Rob Pike - Another Golang at Language Design](https://www.youtube.com/watch?v=uQgWP7zM6mU)
 * [Go Tooling in Action](https://www.youtube.com/watch?v=uBjoTxosSys&t=399s)
 * [Go Proverbs - Rob Pike](https://www.youtube.com/watch?v=PAAkCSZUG1c)

## Go & React Native

 * [Why & how to build your react native code in Go](https://hackernoon.com/react-native-why-and-how-to-build-your-native-code-in-go-9fee492f0daa#.l9jnfmp94)


# Go Tooling

```
cat > main.go
package main
import "fmt"
func main() { fmt.Println("Hello Rik)}
<CTRL-D>
go run main.go
gofmt -w main.go
cat main.go

go build
ls ./demo
```

The word `golang` here to help search engines..