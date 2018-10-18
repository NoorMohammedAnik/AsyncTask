# AsyncTask
Android Async Task Example

* In Android, AsyncTask (Asynchronous Task) allows us to run the instruction in the background and then
synchronize again with our main thread.

* AsyncTask class is used to do background operations that will update the UI(user interface). 
Mainly we used it for short operations that will not effect on our main thread.

* By default, our application code runs in our main thread and every statement is therefore execute in a sequence.
If we need to perform long tasks/operations then our main thread is blocked until the corresponding operation has finished.
For providing a good user experience in our application we need to use AsyncTasks class that runs in a separate thread.
This class will executes everything in doInBackground() method inside of other thread which doesn’t have access to the GUI where
all the views are present. The onPostExecute() method of this class synchronizes itself again with the main 
UI thread and allows it to make some updating. This method is called automatically after the doInBackground method finished its work.

* In Android, AsyncTask is executed and goes through four different steps or method. Here are these four methods of AsyncTasks.

* 1. onPreExecute() – It invoked on the main UI thread before the task is executed. This method is mainly used to setup the task for instance by showing a ProgressBar or ProgressDialog in the UI(user interface).

* 2. doInBackground(Params) – This method is invoked on the background thread immediately after onPreExecute() finishes its execution. Main purpose of this method is to perform the background operations that can take a long time. The parameters of the Asynchronous task are passed to this step for execution. The result of the operations must be returned by this step and it will be passed back to the last step/method i.e onPostExecutes(). This method can also use publishProgress(Progress…) to publish one or more units of progress. These values will be published on the main UI thread in the onProgressUpdate(Progress…) method.

* 3. onProgressUpdate(Progress…) – This method is invoked on the main UI thread after a call to publishProgress(Progress…). Timing of the execution is undefined. This method is used to display any form of progress in the user interface while the background operations are executing. We can also update our progress status for good user experience.

* 4. onPostExecute(Result) – This method is invoked on the main UI thread after the background operation finishes in the doInBackground method. The result of the background operation is passed to this step as a parameter and then we can easily update our UI to show the results.
