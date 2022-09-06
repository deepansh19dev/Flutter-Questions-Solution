# Flutter-Questions-Solution<h1>

1. Hot Reload and Hot Restart

</h1>

<p>
 Hot reload implements the change in your UI in a couple of seconds, without reloading the whole app or messing with inputs and variables. Hot Reload takes less time ,then Hot restart.
 If you are using States in your application then Hot Reload preservers the States , so they will not update on Hot Reload our set to their default values.

Hot restart takes more time than hot reload, and it destroys or rebuilds the state value and rebuilds it to the default. The app widget tree is completely rebuilt with a newly typed code. This takes about 23-30 seconds compared with the default app restart time. It doesn't restart the whole application rather it rebuild the app widget tree. Restarting the whole app would’ve done the same thing, but it would’ve done it in 40 seconds. Therefore, Hot restart saves developers time.

</p>

<h1>

2.Custom Widgets

</h1>

<p>
when we want a custom look and feel to our app, and we know that there will be a repetition of a particular widget.
Ways to create custom widgets

a Create a new dart file with desired functionality and used this file as widget
b You can draw on canvas which Flutter provides using Custom Painter

</p>

<h1>

3.Method Channel

</h1>

<p>
With the help of method channel platform specific code can be accessed

</p>


<h1>

4 Event Loop

</h1>

<p>
An event loop’s job is to take an item from the event queue and handle it, repeating these two steps for as long as the queue has items.The items in the queue might represent user input, file I/O notifications, timers, and more.

An isolate is what all Dart code runs in. It’s like a little space on the machine with its own, private chunk of memory and a single thread running an event loop. So the event loop is the part of isolates where all dart code runs.

</p>

<h1>

 Coding Questions

</h1>

```
return Scaffold(
      body:  Wrap(
        children: const [
          Chip(label: Text('I')),
          Chip(label: Text('am')),
          Chip(label: Text('looking')),
          Chip(label: Text('for')),
          Chip(label: Text('a')),
          Chip(label: Text('job')),
          Chip(label: Text('and')),
          Chip(label: Text('I')),
          Chip(label: Text('need')),
          Chip(label: Text('a')),
          Chip(label: Text('job')),
          Chip(label: Text('I')),
          Chip(label: Text('am')),
          Chip(label: Text('looking')),
          Chip(label: Text('for')),
          Chip(label: Text('a')),
          Chip(label: Text('job')),
          Chip(label: Text('and')),
          Chip(label: Text('I')),
          Chip(label: Text('need')),
          Chip(label: Text('a')),
          Chip(label: Text('job')),
        ],
      ),
    );

```
```
final String postsURL = "https://inshorts.deta.dev/news?category=all";

  Future<List<NewsItem>> getPosts() async {
    final url = Uri.parse(postsURL);
    final response = await http.get(url);
    final jsonResponse= jsonDecode(response.body);
    List<dynamic> body=jsonResponse['data'];
    List<NewsItem> posts=[];
    for (var singleUser in body) {
      NewsItem item = NewsItem(
          content: singleUser["content"],
          date: singleUser["date"],
          imageUrl: singleUser["imageUrl"],
          title: singleUser["title"]);

      //Adding user to the list.
      posts.add(item);
    }

      return posts;
  }

```

```
Future<void> callFun() async{
     final sum = await compute(longOperationMethod, 1000000000);
   }

String longOperationMethod(int value) {
  var counting = 0;
  for (var i = 0; i <= value; i++) {
    counting = i;
  }
  return '$counting! times I print the value';
}

```
