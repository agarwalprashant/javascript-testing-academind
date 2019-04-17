# javascript-testing-academind
JavaScript Testing Introduction Tutorial - Unit Tests, Integration Tests &amp; e2e Tests - video Url - https://www.youtube.com/watch?v=r9HdJ8P6GQI


hi everyone welcome to this video in
00:04
this video I'm gonna dive into one topic
00:06
that a lot of people are struggling with
00:08
or are afraid of and that is testing
00:11
your code in this video specifically
00:13
testing JavaScript code testing can be
00:16
or should be an important part of any
00:19
major project you're working on and
00:21
still a lot of people don't do it
00:23
because it looks too complex it's too
00:25
unclear how it works and so on in this
00:27
video I'll take a look at what exactly
00:29
testing is why we would want to test and
00:32
then of course most importantly how to
00:34
test our code and you will learn that
00:36
there is no reason to be afraid it's
00:38
actually pretty easy to get started with
00:40
testing so let's dive in
00:45
now what is testing and why would we
00:48
want to test now testing when you hear
00:50
it for the first time sounds pretty
00:52
obvious pretty straightforward we are
00:54
writing an app we're creating an
00:56
application and we simply test it right
00:58
we had a feature we open the browser and
01:01
we test our application and that is
01:03
indeed how you will continue to work
01:05
even if you do add this kind of testing
01:08
I'll dive in in this video so testing
01:10
manually still is something that makes
01:12
sense you want to see your application
01:13
run so in the end the idea always is
01:16
that we have our code and we have some
01:18
expected result so if we write some code
01:21
and then we go into the browser and test
01:23
this code we have some idea of what
01:26
should happen we want to open that modal
01:28
we want to add that user when we click
01:31
that button something like this so we
01:33
have our expected results in mind and
01:35
then we simply test our application and
01:37
if we are successful we are fine with
01:40
that we can continue with writing the
01:42
next piece of code and if we're not
01:44
happy with the result well then we can
01:46
modify our code and fix the issue or
01:49
adjusted such that it works in the way
01:51
we want now the idea of JavaScript
01:54
testing or code testing when you read it
01:57
like this is that we automate this
01:59
testing part so that we automate it so
02:02
that we don't have to manually test
02:04
everything in our application now we
02:07
will probably still test everything
02:09
manually but automated tests can be run
02:12
whenever we change something in code to
02:15
see if that affects any part of our
02:17
application without us having to test
02:19
everything manually again that is the
02:21
idea behind automated testing that we
02:24
can see breaking changes were issues in
02:27
our code may be introduced by a change
02:30
in place a in a totally different place
02:32
of our app that we can see this
02:34
instantly that is one of the major
02:36
benefits of writing tests so that is
02:39
also one answer to the question why
02:41
would we want to test we want to get an
02:43
error and CDR if we break our code we
02:45
want to see that immediately without us
02:48
testing everything manually we might
02:49
still do manual testing but it's still
02:52
worth a lot to have a suit of predefined
02:55
automated tests that we can run to
02:58
quickly
02:58
see did this change break anything well
03:01
with well-written tests we'll get the
03:03
answer right away we'll also save time
03:06
if we don't have to test everything
03:07
manually over and over again and we are
03:10
all forced to think about possible
03:12
issues or bugs
03:13
when writing our tests we have to think
03:16
about what do we want to test how do we
03:19
write a test that makes sense and I'll
03:22
dive into that in this video already we
03:24
also can integrate it into our build
03:26
workflow this is something more advanced
03:29
but there I mean you could have a build
03:31
workflow where you push a commit so a
03:34
get commit to your code repository like
03:38
github and then you have a workflow that
03:40
automatically is triggered where this
03:42
code is then tested in the cloud on some
03:44
server and if the test succeeds it's
03:46
maybe deployed automatically so you can
03:49
build a very complex deployment chain
03:51
there and tests are then an integral
03:53
part of ensuring that no breaking or
03:55
invalid code is deployed so that is also
03:58
an advantage of tests or something you
04:00
can use tests or we can also break up
04:03
complex dependencies and that is also
04:05
something I'll show in this video we
04:07
have to make sure we write code that can
04:10
be split up that is modular because this
04:12
will make testing easier and ultimately
04:14
it will make working with our code
04:16
easier and it improves our code
04:19
therefore since we are forced to follow
04:21
certain patterns or to write code in a
04:24
certain way or at least that will make
04:26
testing easier we will write better code
04:29
all together so these are a lot of great
04:32
advantages but they might still be a bit
04:34
abstract when you have not written any
04:37
tests so let's dive into testing soon
04:40
but not before I try to answer one other
04:42
question and that is which types of
04:45
tests do we have I'm talking about
04:47
automated tests so some code we write
04:50
that tests our code so code that tests
04:53
code that is a good description of what
04:55
testing is or what automated testing is
04:57
I guess and there we have different
04:59
kinds of tests we have some tests that
05:02
test a fully isolated piece of code
05:04
let's say a function that takes some
05:07
input and returns some output we can
05:09
test such a function with a test because
05:12
it
05:12
has a clearly defined structure and we
05:14
can say for input X&Y; we expect to get
05:17
output set and that would be a so-called
05:20
unit test because we test a single
05:22
isolated unit of our application we also
05:27
have some tests that test units with
05:30
some dependencies so we have no isolated
05:34
piece of code anymore but we might have
05:35
a function that calls another function
05:37
let's say and therefore the function
05:39
we're testing depends on the result of
05:41
an average function and that is called
05:44
an integration test because there we're
05:47
testing more than just a single unit we
05:49
test the integration of a feature into
05:51
another feature so to say we also have
05:54
the full flow which we can test or the
05:56
user interface so the full application
05:59
or a part of the full application and
06:01
this is a so-called end-to-end
06:03
or also a user interface test the idea
06:05
here is really that we do what we could
06:08
do manually as well in the browser but
06:10
that we write kind of an automated
06:12
script that executes a certain series of
06:14
steps for us and then we can check if
06:16
the result is the result we expected to
06:19
get now these kinds of tests have a
06:21
different complexity unit tests are
06:23
relatively easy to write because you
06:25
have a small unit and you know it's easy
06:29
to infer what you want to get as a
06:31
result the more dependencies you add the
06:34
more complex it becomes because it gets
06:36
harder to differentiate between what
06:38
exactly is causing an error is it a
06:40
dependency or the function that uses the
06:43
dependencies also you might have some
06:45
dependencies that reach out to a server
06:47
and fetch data that is also a complexity
06:50
you have to handle and it will show you
06:51
how to handle this in a separate video
06:53
and the full user interface test is the
06:56
most complex one because there you have
06:58
to define every step that should be
07:00
executed and cleverly think about what
07:02
you want to test and what you want to
07:04
expect there now all the due to this
07:07
complexity we write tests in a different
07:10
frequency we typically have a lot of
07:12
unit tests because if you test every
07:15
unit of your application and it works
07:16
correctly
07:17
you can kind of infer that the overall
07:19
application will also work correctly so
07:22
we will have a lot of unit tests we then
07:24
have some integration tests
07:26
to rule out that two individually
07:29
working units don't work anymore if you
07:31
combine them and we have a few UI or
07:35
end-to-end tests to test some steps or
07:38
some flows in our application in the
07:41
browser in an automated way so these are
07:43
the kinds of tests and in this video I
07:45
will show you all three already
07:47
and with that I'd say it's enough of the
07:49
theory let's start writing some tests
07:51
for that I prepared a little demo
07:53
project to which you find a link below
07:55
the video of course and you can simply
07:58
download that run npm install in the
08:01
extracted folder to set up all the
08:04
dependencies I have here I don't have
08:06
many dependencies I only use webpack and
08:08
then we have a very simple application
08:10
here in app J's a JavaScript application
08:12
front-end JavaScript where I import some
08:16
bad stuff and then have some code to
08:18
basically set up an event listener to a
08:20
button and add a user to a list of users
08:24
when we click that button
08:25
I got u tilde s which holds D the
08:29
functions and importing into AB KS I'm
08:31
using node.js module syntax here simply
08:35
because that's a bit easier to test and
08:36
doesn't require a complex build workflow
08:39
setup on which I simply didn't want to
08:41
focus in this video but I use webpack to
08:43
then bundle this all up and get a main
08:45
J's file which is the file we then use
08:48
now what you can do is you can simply
08:49
double-click index.html I got no dev
08:53
server and place here or anything like
08:55
that simply to not focus too much on the
08:58
front and workflow and if you did double
09:01
click on that file this is what you'll
09:02
get you can enter some data and add a
09:05
user and that is all we can do here so
09:07
it's a relatively simple app but that is
09:09
great for starting with testing because
09:12
we can easily confirm if our tests make
09:14
sense if they do test something we would
09:16
test manually as well so this is the
09:19
application and now let's write some
09:23
tests now for writing tests we need some
09:25
external tools we need some tools that
09:28
help us with creating these tests what
09:30
do we need we typically need three kinds
09:33
of tools we need a test runner which is
09:36
simply a tool that executes our tests
09:39
and summer
09:39
the results and gives us some output on
09:41
the results we can use something like
09:44
maca there that is a popular test runner
09:47
we also have assertion libraries and
09:50
there we define our tests that logics
09:52
are expected outcomes
09:54
so these assertion libraries give us
09:56
tools to define expectations to define
09:59
comparisons conditions we want to check
10:02
as part of our tests they are chai is a
10:05
common or a popular assertion library
10:08
though what we will use is a very
10:10
popular library for both running tests
10:13
and asserting and that is just just as
10:16
relatively new or at least it was
10:18
rewritten and not that long ago and it's
10:21
a very popular library for writing tests
10:24
because of this Bopha test Runner and an
10:26
assertion library and it's really
10:28
powerful and a lot of fun to work with
10:31
for end to end we also sometimes need a
10:35
headless browser so basically a browser
10:37
where we don't have to click manually
10:39
but where we can use the browser API the
10:41
Dom and so on without a user interface
10:43
necessarily because we'll analyze it in
10:46
code anyways and there we can use puppet
10:49
here which is a very popular solution
10:51
for that we need to add headless browser
10:53
mostly for ant to end testing whereas
10:56
the test Runner and the search library
10:57
are also needed for that but also then
11:00
are the only things we need for a unit
11:02
and integration tests now let's start
11:05
with jest and with unit tests and you
11:08
can simply google for a jest to find
11:10
just j s dot io t official webpage of
11:13
chess chairs and there i can only
11:15
recommend trying that out getting
11:18
started diving into the official Docs to
11:20
learn way more but of course I'll also
11:21
walk you for all the basics in my videos
11:24
here so we'll start installing just now
11:27
and for that let's switch over to our
11:29
project and in there
11:31
let's run npm install - - save dev just
11:36
because just will be a development
11:38
dependency of our project and it will be
11:41
the tool we use for running our tests
11:43
and for checking our outcomes or for
11:45
writing some conditions some assertions
11:47
as its called
11:48
so this will now install and with it
11:52
installed we can
11:53
right our first test and it will write
11:55
my test for functions defined in Utah je
11:58
s and their this first function makes up
12:01
for a great first unit test it has no
12:04
other dependencies because it does not
12:06
call any other function it does not
12:08
reach out to the web or anything like
12:10
that it simply takes input two arguments
12:13
and returns an output and this would be
12:15
a great example for a simple unit test
12:18
we can write now to write a test for
12:20
this function you create a separate file
12:23
into which you'll store your tests and
12:25
you typically named it file like to file
12:27
your testing Guto and then dot spec or
12:30
dot test is and the name is up to you
12:33
jest will automatically detect files
12:35
with dot test or dots back in them and
12:37
we'll run them automatically once you
12:39
run just which we'll do in a second so
12:42
now I have my util test dot J's file and
12:45
I want to test my generate text function
12:47
for that I first of only to import it
12:50
here I will use destructuring syntax
12:53
here to require something from Yuto so
12:59
from that you tell file where the core
13:01
code is stored and then the structuring
13:03
syntax simply means I pull out some
13:05
items from the object which isn't the
13:07
end exported by the util file and it
13:09
will pull out the generate text function
13:11
so essentially I import the generate
13:13
text function into my util test J's file
13:16
and by the way this is the native way of
13:18
importing ingest tests you could think
13:22
that you can also use like es6 imports
13:26
if you had respective exports in your
13:28
file of course something like this but
13:31
this will not work not only because I'm
13:33
not using es6 Explorer exports here that
13:36
is also a problem but even if I would
13:38
use them this is not a syntax natively
13:41
supported by jest this note is like
13:44
import syntax is supported by jest and
13:47
therefore I also wrote my code to use
13:49
nodejs exports because that made it
13:52
easier to implement just obviously you
13:54
can also make it work with es modules
13:56
like you use it and react or angular
13:58
apps but there you need a more complex
14:01
build workflow you need some additional
14:03
packages and I did not want to spend a
14:06
lot of time
14:06
on the setup I want to spend time on
14:09
testing therefore I use this syntax so
14:12
now I'm using gel or I'm importing
14:13
generate text in this file now we can
14:16
write our first test and for that we can
14:18
simply write tests here this is a
14:20
function which is now globally available
14:22
or which will be globally available when
14:25
we run our test with just so there's a
14:28
function provided by just in the end and
14:30
this function allows us to define a
14:32
single test now we can give that test a
14:35
name that's the first argument we're not
14:37
really a name more of a description you
14:39
could say something like should output
14:43
name and age typically you kind of
14:46
define what you want to test in this
14:50
name or in this description so which
14:51
output are you testing for you try to
14:54
put that in your description ultimately
14:57
you can put whichever text you want in
14:58
here but it should be kind of
15:00
descriptive the second function argument
15:03
is then an anonymous function which you
15:05
pass in with just a function jest we'll
15:08
execute to rerun your test so in this
15:11
function you add your testing code your
15:14
code that will be executed and now here
15:17
we can generate some text by calling
15:20
generate text and storing that in a text
15:22
constant and there will pass in max and
15:24
29 let's say now that is also what I
15:28
tested here manually entering max in 29
15:31
added a new item with text max and 29
15:34
years old now I'm effectively testing
15:36
that part where this text is generated
15:39
so not where the whole item is generated
15:41
but only this text max 29 years old is
15:45
what I expect as an output of generate
15:47
text because if we have a look at
15:49
generate text well then we return a text
15:51
here where we have to name and then in
15:54
brackets
15:54
29 or whatever the age is 29 years old
15:58
now if we have that expectation we
16:01
should formulate it here in the test and
16:03
we do this with the expect function
16:05
which is also provided by jest now if
16:08
you would use a different setup with
16:10
let's say mocha and chai then test would
16:13
be a function defined by your test
16:14
Runner
16:15
whereas expect would be a function
16:17
provided by your assertion library and
16:19
Moe
16:20
search libraries work with the expect
16:22
function because tests are pretty
16:24
descriptive in terms of function names
16:26
we write a test and then we expect
16:28
something
16:29
now here we expect that text so we pass
16:34
the thing we want to look into you we
16:37
want to compare we expect text is equal
16:41
to a specific text we do this with a
16:44
bunch of helper functions that we can
16:46
now chain on our expectable object here
16:50
and there you see we have a lot of
16:53
functions where we could say we expect
16:55
text to be not a number for example or
16:58
to be null or just to be and then here
17:02
as an argument to the to be function we
17:05
pass the value we expect text to be that
17:08
could be a number but that could be also
17:11
max twenty nine years old which is
17:14
exactly the output we do expect to get
17:16
because of this day output we can also
17:17
see here and now with that we have our
17:21
first tests to find now to run this test
17:24
with the jest package I will tweet my
17:26
package JSON file there we have just
17:29
installed and we have a script up here
17:32
the test script which is kind of invalid
17:34
right now here I will just run just and
17:37
this will automatically search for files
17:39
with dot test or dots back in the name
17:41
and execute them or which end with dot
17:45
test rjs or dot spec j/s I should say so
17:48
now with that added we can simply run
17:51
npm test down there in a normal terminal
17:54
navigated into the project folder and
17:56
just will automatically execute all our
17:58
testing files and here we get a
18:00
beautiful green output it found one test
18:04
which passed and there we see the one
18:06
test which passed successfully where it
18:09
should output name and age and that
18:11
succeeded now this is great because now
18:14
if we ever change something here let's
18:17
say we accidentally output the age here
18:20
too we changed something in that
18:22
function and the original function and
18:24
we break it if we save this and then we
18:27
run our tests again we now actually get
18:30
a failed test and that is exactly where
18:32
tests can help
18:34
a lot we get a failed test we see which
18:37
test failed should output name and age
18:39
and just even gives us some information
18:41
on what failed there we see that we
18:45
expect that max 29 years old but we got
18:48
29 29 years old and this now helps us
18:52
debug our code and fix our code of
18:54
course this is kind of a constructed
18:56
example here but you could have a typo
18:58
like this you could be misusing some
19:00
variable or some argument and now if we
19:03
fix that we can indeed run this again
19:06
and get that test passed by the way you
19:09
can also watch with chests you can add -
19:12
- watch here and now if you run npm test
19:16
just will actually keep on watching and
19:19
you can control the watcher with the
19:21
shortcuts that are shown there for
19:23
example force a run of all your tests
19:26
again or whatever you want to do and it
19:29
also means that now if I do change my
19:32
file here and I save just automatically
19:35
reruns my tests so this is great having
19:38
this run all the time and therefore
19:39
ensuring that we get errors right as we
19:42
change something so that is another
19:43
great option and that is our first unit
19:47
test here now this is a first simple
19:49
unit test now before we move on to
19:51
integration tests just a quick example
19:53
for a different kind of test that could
19:56
also make sense we should also make sure
19:58
that it does not just return the valid
20:00
response here because we can get this
20:04
with this trick as well if I copy the
20:07
output there I can also just use return
20:12
and then this text here and if I do that
20:17
then my first test will always succeed
20:26
if I quickly comment out that second
20:28
snippet so my test will not always
20:30
succeed but I have an error in my
20:32
function and we have a second test we
20:34
can add a second test where we confirm
20:36
that this is not the case so let's say
20:39
we say should output data less text or
20:45
whatever you want to name it and there I
20:48
could also generate a text with generate
20:51
text but I pass an empty string and I
20:55
pass null as a number here and then I
20:58
can't expect that text should be well
21:03
what should it be like it should be
21:05
basically just a blank and then nothing
21:10
years old right well let's give this a
21:13
try if I save Det it fails because I
21:17
always get back max 29 years old because
21:19
I broke that function I had a false
21:22
positive for the first test because I
21:24
returned the value which I expected
21:26
there but the value didn't take the
21:27
inputs into account now I can fix this
21:30
of course and return to the function for
21:33
him I had before and now the second text
21:39
will fail fail because there whoops I
21:43
should expect null years old of course I
21:45
passed an all not nothing and now there
21:47
I passed you and I have confirmation
21:49
that I don't have a false positive here
21:51
so we're adding a second test like this
21:53
might make sense as well to kind of
21:56
check for the opposite or check the same
21:58
thing with different arguments though
22:00
you could do the same in one of the same
22:03
tests you can have multiple expects here
22:06
too so you could generate an ax 28 here
22:11
as well and then simply add another
22:13
expectation here text 2 to be an ax 28
22:20
years and now this should all do pass
22:23
but having such double checks that is
22:25
the main thing can make a lot of sense
22:27
to avoid false positives and here I have
22:30
a double check as well as testing the
22:32
opposite so what happens if I call that
22:35
function correctly
22:36
what happens if
22:37
has nothing for example well then we
22:40
would expect undefined undefined here
22:48
right and that would be a test that
22:51
could also make sense so I'll delete
22:53
that for now I'll leave it at this
22:54
simple unit test but you should be aware
22:56
of the fact that you can write multiple
22:58
unit tests for one and the same thing
23:00
then you can check more than one thing
23:02
in a unit test and that you might also
23:04
want to check for false positives or for
23:06
opposites but now let's move on to
23:08
integration tests so let's now write an
23:12
integration test and for integration
23:14
testing if we have a look at all our
23:16
code which function could we use there
23:18
well we got the app.js file we got add
23:21
user which uses a lot of other functions
23:23
which has a lot of dependencies so
23:25
testing this function would be an
23:27
integration test but this is a function
23:29
that that doesn't either take an input
23:30
nor return an output it's that it's a
23:33
function that really added something
23:34
that dawn so this is something which you
23:36
might want to test in an end-to-end
23:38
testing scenario or in a user interface
23:40
test but an integration test would be
23:44
kind of hard here we would have to do a
23:46
lot of manual Dom interaction inside of
23:49
our test which you can do but which you
23:51
might not want to do instead there is
23:54
something else I can test and that is
23:56
basically a part of that function you
23:57
could say in the end what I'm doing in
23:59
the add user is I do select a couple of
24:02
elements then I do validate the input
24:04
and then I generate a text based on the
24:07
input now we could outsource this init
24:09
into a separate function and that is the
24:11
part of writing modular code that I
24:13
mentioned earlier your forstride modular
24:15
code which also makes your code easier
24:17
to manage and reuse though so in you
24:20
told Jas I can export a new function and
24:22
let's name it
24:23
check and generate or whatever you want
24:26
to do now check and generate will get a
24:30
name and a age as an input and then I
24:34
will go to my app J's file and I will
24:36
grab that validation code and move it
24:39
into check and generate to validate
24:41
input for and now that's important for
24:44
the name here and then there for the age
24:47
like this and then if we make it past
24:50
this
24:51
if block I will return a call to
24:53
generate text where a pass name and age
24:56
because that is what I then returned
24:57
here I returned to checked text so in
25:01
app days where I'm using this output
25:04
text is in the end just a result of my
25:07
call to check and generate I don't need
25:09
validate input here anymore
25:11
I don't need generate text anymore I'll
25:13
just import check and generate this new
25:15
functional import data and app chess and
25:17
down there out for text is the result of
25:21
check and generate I can move that up
25:24
here and here I can now simply check if
25:27
not output text so if we did return
25:32
let's say false here we return false and
25:36
validation fails so if this is returned
25:38
and therefore if this is not true ish if
25:40
it is false for example then it will
25:42
return an add user to and it will not
25:44
continue creating that element so now it
25:47
is this the tweak to add user function
25:48
and this gives us the check and generate
25:50
function which is great to use in an
25:52
integration test so let's write the test
25:55
for it and I want to test if my validity
25:58
works correctly and I then get the
26:00
expected text back so it should generate
26:04
a valid text output or something like
26:07
this and then here in this function I
26:10
will test my check and generate function
26:14
which I therefore have to import and I
26:16
can simply create my text with check and
26:19
generate and I've has max and 29 here
26:22
and I would expect this text to be equal
26:29
to max 29 years old so my expectation
26:34
actually is the same as in this unit
26:36
test but it's not a simple unit test
26:38
because the function we're testing has
26:40
more to it we could fail because
26:42
validation fails or because generate
26:45
text fails
26:46
however generate text is kind of ruled
26:48
out because we have a separate unit test
26:50
for this and this is also how you want
26:52
to write your tests by the way you want
26:54
to ensure that you drill down like to
26:56
the smallest possible level and write
26:59
unit tests for all your units so write a
27:02
test for generate text would also be
27:04
worth right
27:05
one for validate input and then your
27:07
integration tests really just rely on
27:10
the unit's being tested and ensure that
27:12
the units also work together well so
27:14
desert stand the idea behind an
27:16
integration test so here I have this
27:19
test and if I now save this it actually
27:22
fails now I get an error that Valley
27:26
that input is not defined here and that
27:30
is true because I do export validate
27:32
input I don't need to do that anymore
27:34
I should instead created or define it as
27:39
a constant the same is true for generate
27:41
text so that I can use these functions
27:43
directly in util J's file and then at
27:46
the bottom I should also export generate
27:49
text and assign the generate text
27:51
constant here and all the export
27:54
validate input maybe and assign that
27:56
constant so that I could use it in our
27:58
files too and now you see my tests
28:01
passed both tests passed now the idea
28:04
about the integration test is that if I
28:07
do change something in my check and
28:09
generate function for example here I use
28:15
my validate input function incorrectly
28:17
so the result of that is used
28:18
incorrectly now it fails and now this is
28:22
a great example of why I have an
28:24
integration test I could have a separate
28:26
test on validate input and validate
28:28
input does work correctly I can tell you
28:30
that but my error is directly here in
28:33
check and generate I'm using the result
28:35
of validate input incorrectly by not
28:37
checking for it being false but for it
28:39
being true and this means if my name is
28:43
valid then I actually returned false
28:45
which is of course the wrong logic in
28:47
check and generate so even though my
28:49
units work correctly the combination of
28:52
the unit's fails because I have an error
28:54
here and this again shows you the power
28:56
of tests and why integration tests make
28:59
sense too and unit tests alone could not
29:02
be enough because all units could be
29:04
working if you're combining them
29:05
incorrectly you still have a problem so
29:08
now it's working again though now that
29:11
we had a look at unit tests what they
29:12
are why we use them and integration
29:15
tests let's have a look at end-to-end
29:16
tests or user interface tests
29:18
for this only to install another tool so
29:21
I'll quit my chest process here and I
29:23
will install with safe death puppeteer
29:27
which is a headless version of chrome of
29:30
the Chrome browser so it basically is a
29:31
browser we can use to interact with the
29:34
dom and so on you can even run it in a
29:36
version with the head so where we see
29:38
the browser and we can basically define
29:40
steps that should be executed in that
29:43
browser so that we can automate certain
29:45
processes on our web page and then of
29:48
course tests a result of these processes
29:50
as well
29:51
now this download will take a while
29:53
because it in the end it downloads the
29:55
entire Chrome codebase because well it
29:58
needs that to be able to simulate that
30:01
browser and once it's done I'll be back
30:03
so I'm done installing it let's start
30:06
using puppeteer now and for that I'll go
30:09
to my utility JS file and I will import
30:12
puppet here so import puppet here by
30:17
requiring it from puppeteer like this
30:20
and I will write a new test now and
30:24
there I will just write should click
30:27
around for now we'll fix this later or
30:30
change this later and in this function
30:33
which should be executed here I want to
30:34
use puppet here now how can I use it
30:36
first of all I set up a browser by using
30:39
puppet here launch now this will launch
30:46
a browser with some options which I can
30:48
define here for example I can set
30:50
headless 2 to false to actually run a
30:52
browser with a user interface as well
30:55
you can set a bunch of stuff here and
30:57
you can find it all in the official
30:58
docks of puppet here of course I will
31:01
also set slo-mo here that will basically
31:04
slow down the automated operations so
31:06
that we have a chance of seeing what's
31:08
happening and I'll set it to a value of
31:09
AD and we can also set some arcs here
31:13
which is an array where I can pass - -
31:17
and then for example windows size to
31:19
launch this browser with these arguments
31:21
and windows size allows me to set a
31:24
width height pair so I can set this to
31:27
1920 and 1080 for example like this
31:31
should launch a browser with this size
31:33
and that of course can be great to also
31:35
test if certain responsive features are
31:38
working the way you want so now this
31:41
will create a browser now actually this
31:44
will return a promise so we can use
31:48
async/await here if you want you by
31:50
placing async in front of this pair of
31:54
arguments here or this empty argument
31:56
list and now we can await this to launch
31:59
the alternative would be to just use
32:01
then and catch a single weight and the
32:04
end dust is for you so here I'm awaiting
32:07
this and storing the result and browser
32:08
you could say as a next step I can now
32:13
create a page object by a waiting the
32:17
browser to create a new page like this
32:23
now I also need to tell the browser
32:25
which page to load and I'll grab my URL
32:28
here and then we can say page go to and
32:33
then you enter your URL which should be
32:36
loaded and you also should have wait
32:38
this because all these browsers related
32:40
things are of our promises that simply
32:43
take some time to execute so you have to
32:45
await each step so now the should open a
32:48
browser and load this page let's try
32:51
this by running NPM test and it should
32:54
indeed open up a brand new window in
32:58
chromium which is basically like the
33:00
chrome word the core functionality of
33:04
chrome and you'll see that this is being
33:06
tested controlled by automated test
33:09
software so this was opened
33:11
automatically now let's go back and
33:14
let's add some logic here we don't just
33:17
want to go to that page let's say we
33:19
also want to enter something for that I
33:22
want to enter something into my input
33:25
with the ID name and age so in my test I
33:28
will await a step where I use that page
33:31
where I navigated to my app where I will
33:35
then click into the field with that
33:38
selector so click takes the selector off
33:40
the item it should click on once I click
33:44
there
33:45
we'll type and again you can find all
33:47
commands in the official puppeteer Docs
33:49
so you can really like instruct browser
33:52
the headless browser what to do so I
33:54
want to type and I want to type into the
33:56
same input and we wouldn't have to click
33:58
on at first but I want to simulate all
34:00
the steps a user would do I don't want
34:03
to insert let's say and I here to mix it
34:06
up
34:06
not always max so now I type in there I
34:09
will repeat these steps once I type the
34:12
name for the H so for the H field I will
34:16
enter 20 a let's say if you save that it
34:23
will open up a new window where you can
34:25
see that it enters these things now we
34:30
can now also add another step and click
34:33
on this button at the bottom of our page
34:37
so in fjs in the end it's this button
34:39
we're listening on for an event here
34:42
with ID button add user can grab that
34:45
selector and make sure we click on that
34:47
in our setup and now we get a full flow
34:50
setup
34:53
where you see that this gets entered and
34:55
then we click this button here at the
34:58
end you also saw that it didn't add an
35:02
item and this already shows us that
35:04
writing this text was not the worst idea
35:06
because it looks like something was
35:08
broken and indeed here in our automated
35:12
test if we open the developer tools we
35:15
see it that it didn't find the validate
35:17
input function here so since that was
35:20
missing or is missing
35:21
we have to check our util J's file and
35:24
see what's wrong with validate input in
35:27
here I'm using validate input here and
35:30
I'm defining it as a function here but
35:32
one thing I never did is I never
35:34
recompiled my code that's something we
35:37
have to do because the code that gets
35:39
imported in the browser is packed with
35:41
webpack and I never recompiled it after
35:44
changing my code so in a separate
35:46
terminal window I'll quickly run NPM
35:48
start to get web pack to run my code
35:51
it'll now also watch my code and
35:52
recompile if I change something and with
35:57
that it should have executed your test
35:59
automatically in case it didn't simply
36:01
add a blank and reopen your browser and
36:06
enter and it will reopen the browser and
36:09
execute this and now you see this works
36:11
and this is puppet here being used for
36:13
automated testing with a graphical user
36:15
interface now obviously we can automate
36:17
this a bit more and check the result
36:19
programmatically now to see if we got
36:22
the expected outcome because what I can
36:24
now do is I can also wait and now that
36:27
everything executed I can check if
36:29
something is the case for example I can
36:31
check for the existence of this list
36:33
item with a class of user item being
36:36
added to it so in my test I can await my
36:41
page and there I can use dollar email to
36:44
get access to an element and I will look
36:48
for the first element with a class of
36:52
user item and I pass a function as a
36:55
second argument to evil where I then
36:58
define what I want to do with the
37:00
element I select it there and here I
37:02
will get an element as an input and
37:06
for example return the text content and
37:08
this means that now the result of this
37:11
function will be returned by this
37:12
overall promise so I can store it here
37:15
final text for example will be the text
37:18
that I fetched from this element that
37:20
was created and now I can expect final
37:24
text QB Ana 28 years old now it's again
37:31
checking for that text but it's now
37:33
using the full flow in the browser it's
37:35
not just the unit or integration test as
37:37
we have it up there
37:38
it's really going through all the steps
37:40
we would execute manually as well and
37:42
then of course we should have that text
37:44
but we could check anything here we
37:45
could also check for the existence of
37:48
this class and we implicitly do so
37:50
because if that class would not be there
37:52
we couldn't select the element by it and
37:54
therefore final text would certainly not
37:56
be that text but now if I save this it
37:59
executes all our steps here and it
38:05
actually fails here because it basically
38:08
timed out that's just a limit setup by
38:11
just to ensure that our tests don't take
38:13
too long what we can for do for that is
38:16
the test function actually takes a third
38:20
argument and that is the maximum timeout
38:22
and we can set this to 10 seconds to
38:24
10,000 to increase the time we give our
38:27
browser to complete its operation so
38:29
that it doesn't timeout and now you see
38:31
it finishes successfully because should
38:34
click around to which we should assign a
38:36
better name does give us the result we
38:39
want and here I will now say should
38:42
create an element with text and correct
38:51
class something like this by the way we
38:55
can't of course our also set headless to
38:57
true disabled the slow motion and not
39:00
set these arguments and this will now
39:02
speed up the testing because now it
39:05
doesn't have to go through that step in
39:07
a real browser it does so behind the
39:09
scenes and that's one of the advantages
39:10
of having a headless browser that you
39:13
don't have to watch it execute the steps
39:14
but it can be nice to see the steps you
39:16
can do both and now we got a full
39:20
to a test or a user interface test in
39:22
place - I hope that this video gave you
39:24
a nice introduction to the different
39:26
types of tests we have and why we write
39:28
them and I will have more videos on
39:31
testing where we also write a little bit
39:32
more advanced tests but this video
39:35
hopefully shows you what tests are and
39:37
how will you create them and what their
39:39
advantages are hopefully see you in
39:41
future videos bye
