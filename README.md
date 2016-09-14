# Envato Tuts+ Tutorial: [Practical Concurrency on Android With Hamer][published url]
## Instructor: [Tin Megali][instructor url]

In this tutorial we’ll explore the HaMeR (Handler, Message and Runnable) framework, one of the most powerful concurrency models available on Android. With a hands-on approach, you’ll see how to apply the different possibilities of HaMeR in managing concurrency on Android.

## Sample Project

The code is fully commented and illutrates how to post/send Runnable and Message objects between Threads and how to prepare a Thread using HandlerThread.

The app is composed by:

 - Two Activities, one for Runnable e other for Message calls
 - Two HandlerThread objects
   - WorkerThread to receive and process calls from the UI
   - CounterThread to receive Message calls from the WorkerThread
 - And some utility classes and layout resources

The app has a simple UI with buttons to download some images and start a counter

#### Posting and receiving Runnables with RunnableActivity

1. The RunnableActivity instantiate a background Thread called WorkerThread passing a Handler and a WorkerThread.Callback as parameters
2. The activity makes a call on WorkerThread asking it to download a image.
3. The download is done asynchronously on the background thread
4. The WorkerThread sends the image to the RunnableActivity posting a Runnable to it using a Handler that it received as parameter earlier.
5. Sending and Receiving Messages with MessageActivity

The MessageActivity instantiate a background Thread calledWorkerThread passing a Handler as parameters

1. The activity makes a call on WorkerThread asking it to download a specific image or download a random one.
2. The download is done asynchronously on the background thread
3. The WorkerThread create a Message using the 'key' defined on the MessageActivity and passing the image downloaded as a parameter object.
4. The Message in sent to the MessageActivity using a Handler that WorkerThread received as parameter earlier.
5. The Handler on MessageActivity processes the Message, get the object from it and exhibits on the UI

------

These are source files for the Envato Tuts+ tutorial: [Practical Concurrency on Android With Hamer][published url]

Available on [Envato Tuts+](https://tutsplus.com). Teaching skills to millions worldwide.

[published url]: http://code.tutsplus.com/tutorials/practical-concurrency-on-android-with-hamer--cms-27137
[instructor url]: https://tutsplus.com/authors/tin-megali
