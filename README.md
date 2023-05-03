Download Link: https://assignmentchef.com/product/solved-cpts479-assignment-11
<br>
This homework is essentially the same as Homework 5, except that the quiz questions will be persistently stored using Core Data. My solution to Homework 5 is available on Blackboard Learn. You may use my solution or your own as a starting point. Specifically,

<ol>

 <li>Add the CoreData boilerplate code into your app. You can get this code by creating a new project in Xcode and checking the “Use Core Data” box on the “Choose options for your new project” screen. The code will be at the end of the AppDelegate.swift file. Don’t forget to also include the saveContext line in the applicationWillTerminate method.</li>

 <li>Create a Data Model for a Question. You can add a Data Model to your project by choosing FileàNewàFile and choosing the “Data Model” file under “Core Data”. The data model should consist of a single entity with attributes corresponding to the Question properties: prompt, answer1, answer2, answer3, answer4, answer5, numAnswers, and correctAnswerIndex. Hint: Don’t give the entity the same name as your Question class, or Xcode will get confused. Below is a screenshot of my QuestionEntity.</li>

</ol>




<ol start="3">

 <li>In the Quiz Table View Controller, add a method for fetching questions from CoreData. When the app starts, all the questions stored in CoreData should be loaded and displayed</li>

</ol>

1 in the table view. <em>Do not initialize the app with any sample questions; the initial table of questions should be empty when the app is run for the first time</em>.

<ol start="4">

 <li>In the Quiz Table View Controller, add a method for adding a new question, which should result in adding the question’s data to CoreData. This method should be called upon returning from the Add Question view after tapping Save.</li>

 <li>In the Quiz Table View Controller, add a method for deleting a question. This method should be called when the user swipes-to-delete a question in the table. You will need some way to uniquely identify the CoreData object corresponding to the deleted question, so you can delete that object from CoreData. Below are three ways to do this.

  <ol>

   <li>Maintain a separate array of QuestionEntity objects corresponding to your quiz question array. Modifications to the latter result in modifications to the former along with the appropriate CoreData object inserts and deletes.</li>

   <li>Generate and store a unique identifier with each question, both in the Question class and the QuestionEntity. Then fetch the object having this unique identifier and delete it.</li>

   <li>Each CoreData object has a unique object ID of type NSManagedObjectID. You can store this ID in the Question class (e.g., question.objectID = managedObject.objectID). When you want to delete this question, you can use this ID to access the object directly using managedObjectContext.object(with: question.objectID) and then delete it. Note that the objectID for a new object is assigned only after the context is saved.</li>

  </ol></li>

 <li>Make sure your app can add and delete questions, and that these changes persist even if the app is terminated and restarted.</li>

 <li>Your app should still support all the functionality of Homework 5, including viewing questions that are selected from the table.</li>

 <li>As usual, make sure the auto layout constraints are set so that the view elements are appropriately displayed with no overlap regardless of device orientation.</li>

</ol>


