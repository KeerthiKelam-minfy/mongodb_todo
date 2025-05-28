# mongodb_todo
<pre> 

**Inserting and Updating Records**
	
db.todo_list.insertOne({
status: pending,
description: "iron clothes"})
ReferenceError: pending is not defined
db.todo_list.insertOne({
status: "pending",
description: "iron clothes"})
{
  acknowledged: true,
  insertedId: ObjectId('68373bf644e821fa6897f719')
}
	
	
db.todo_list.updateOne
({description: "iron clothes"}, 
{$set: {CreatedOn: new Date()}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}

	
db.todo_list.insertMany(
[{status: "done", description: "have dinner", CreatedOn: new Date()},
 {status: "done", description: "eat laddoo", CreatedOn: new Date()},
 {status: "pending", description: "eat breakfast", CreatedOn: new Date()},
 {status: "pending", description: "finish assignment", CreatedOn: new Date()},
 {status: "done", description: "do the laundry", CreatedOn: new Date()},
 {status: "pending", description: "brush your teeth", CreatedOn: new Date()},
 {status: "done", description: "drink water", CreatedOn: new Date()},
 {status: "pending", description: "climb the mountain", CreatedOn: new Date()},
 {status: "pending", description: "fly in the sky", CreatedOn: new Date()}]
)
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('68373f0c44e821fa6897f71a'),
    '1': ObjectId('68373f0c44e821fa6897f71b'),
    '2': ObjectId('68373f0c44e821fa6897f71c'),
    '3': ObjectId('68373f0c44e821fa6897f71d'),
    '4': ObjectId('68373f0c44e821fa6897f71e'),
    '5': ObjectId('68373f0c44e821fa6897f71f'),
    '6': ObjectId('68373f0c44e821fa6897f720'),
    '7': ObjectId('68373f0c44e821fa6897f721'),
    '8': ObjectId('68373f0c44e821fa6897f722')
  }
}

	
**Listing all Documents**
	
db.todo_list.find()
{
  _id: ObjectId('68373bf644e821fa6897f719'),
  status: 'pending',
  description: 'iron clothes',
  CreatedOn: 2025-05-28T16:41:18.662Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f71a'),
  status: 'done',
  description: 'have dinner',
  CreatedOn: 2025-05-28T16:51:24.178Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f71b'),
  status: 'done',
  description: 'eat laddoo',
  CreatedOn: 2025-05-28T16:51:24.178Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f71c'),
  status: 'pending',
  description: 'eat breakfast',
  CreatedOn: 2025-05-28T16:51:24.178Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f71d'),
  status: 'pending',
  description: 'finish assignment',
  CreatedOn: 2025-05-28T16:51:24.178Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f71e'),
  status: 'done',
  description: 'do the laundry',
  CreatedOn: 2025-05-28T16:51:24.178Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f71f'),
  status: 'pending',
  description: 'brush your teeth',
  CreatedOn: 2025-05-28T16:51:24.178Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f720'),
  status: 'done',
  description: 'drink water',
  CreatedOn: 2025-05-28T16:51:24.178Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f721'),
  status: 'pending',
  description: 'climb the mountain',
  CreatedOn: 2025-05-28T16:51:24.178Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f722'),
  status: 'pending',
  description: 'fly in the sky',
  CreatedOn: 2025-05-28T16:51:24.178Z
}


db.todo_list.updateMany({}, {$rename: {status: "completed"}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 11,
  modifiedCount: 10,
  upsertedCount: 0
}

	
db.todo_list.updateMany({completed: "pending"}, {$set: {completed: false}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 6,
  modifiedCount: 6,
  upsertedCount: 0
}

	
db.todo_list.updateMany({completed: "done"}, {$set: {completed: true}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 4,
  modifiedCount: 4,
  upsertedCount: 0
}


db.todo_list.updateMany({}, {$set: {completed: false}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 10,
  modifiedCount: 4,
  upsertedCount: 0
}


**Adding Updated Date**
db.todo_list.updateMany({}, {$set: {UpdateOn: new Date()}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 10,
  modifiedCount: 10,
  upsertedCount: 0
}


db.todo_list.updateOne(
{ _id: ObjectId('68373f0c44e821fa6897f71a')}, 
{$set: {completed: true, UpdateOn: new Date()}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}

db.todo_list.updateOne(
{ _id: ObjectId('68373f0c44e821fa6897f71b')}, 
{$set: {completed: true, UpdateOn: new Date()}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
	
db.todo_list.updateOne(
{ _id: ObjectId('68373f0c44e821fa6897f71e')}, 
{$set: {completed: true, UpdateOn: new Date()}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
	
db.todo_list.updateOne(
{ _id: ObjectId('68373f0c44e821fa6897f720')}, 
{$set: {completed: true, UpdateOn: new Date()}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}


**Using enum for setting priority for tasks with values High, Medium, and Low**

function insertTodo(todo) {
  const allowedPriorities = ["High", "Medium", "Low"];

  if (!allowedPriorities.includes(todo.priority)) {
    throw new Error(`Invalid priority value: ${todo.priority}`);
  }

  return db.todo_list.insertOne(todo);
}
[Function: insertTodo]

	
insertTodo({description : "charge my phone", completed: false, CreatedOn: new Date(), UpdatedOn: new Date(), priority: "High" })
{
  acknowledged: true,
  insertedId: ObjectId('683746d544e821fa6897f723')
}

	
insertTodo({description : "sleep early", completed: false, CreatedOn: new Date(), UpdatedOn: new Date(), priority: "Urgent" })
Error: Invalid priority value: Urgent


db.todo_list.updateMany(
  { priority: { $exists: false } },
  { $set: { priority: "Medium" } }
)
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 10,
  modifiedCount: 10,
  upsertedCount: 0
}


db.todo_list.updateOne({_id: ObjectId('683746d544e821fa6897f723')}, {$set: {status: true, UpdatedOn: new Date()}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}


**Counting the number of Documents**
db.todo_list.countDocuments()
11


**Deleting a record and counting again**
db.todo_list.deleteOne({description: "finish assignment"})
{
  acknowledged: true,
  deletedCount: 1
}

	
db.todo_list.countDocuments()
10


**Sorting**
db.todo_list.find().sort()
{
  _id: ObjectId('68373bf644e821fa6897f719'),
  description: 'iron clothes',
  CreatedOn: 2025-05-28T16:41:18.662Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f71a'),
  description: 'have dinner',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:16:40.131Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f71b'),
  description: 'eat laddoo',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:17:45.163Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f71c'),
  description: 'eat breakfast',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f71e'),
  description: 'do the laundry',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:18:46.771Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f71f'),
  description: 'brush your teeth',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f720'),
  description: 'drink water',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:19:18.611Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f721'),
  description: 'climb the mountain',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f722'),
  description: 'fly in the sky',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}
{
  _id: ObjectId('683746d544e821fa6897f723'),
  description: 'charge my phone',
  completed: false,
  CreatedOn: 2025-05-28T17:24:37.983Z,
  UpdatedOn: 2025-05-28T17:50:47.418Z,
  priority: 'High',
  status: true
}


**Sorting based on a particular field**
db.todo_list.find().sort({description: 1})
{
  _id: ObjectId('68373f0c44e821fa6897f71f'),
  description: 'brush your teeth',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}
{
  _id: ObjectId('683746d544e821fa6897f723'),
  description: 'charge my phone',
  completed: false,
  CreatedOn: 2025-05-28T17:24:37.983Z,
  UpdatedOn: 2025-05-28T17:50:47.418Z,
  priority: 'High',
  status: true
}
{
  _id: ObjectId('68373f0c44e821fa6897f721'),
  description: 'climb the mountain',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f71e'),
  description: 'do the laundry',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:18:46.771Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f720'),
  description: 'drink water',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:19:18.611Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f71c'),
  description: 'eat breakfast',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f71b'),
  description: 'eat laddoo',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:17:45.163Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f722'),
  description: 'fly in the sky',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f71a'),
  description: 'have dinner',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:16:40.131Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373bf644e821fa6897f719'),
  description: 'iron clothes',
  CreatedOn: 2025-05-28T16:41:18.662Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}


	
db.todo_list.find().sort({description: -1})
{
  _id: ObjectId('68373bf644e821fa6897f719'),
  description: 'iron clothes',
  CreatedOn: 2025-05-28T16:41:18.662Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f71a'),
  description: 'have dinner',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:16:40.131Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f722'),
  description: 'fly in the sky',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f71b'),
  description: 'eat laddoo',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:17:45.163Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f71c'),
  description: 'eat breakfast',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f720'),
  description: 'drink water',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:19:18.611Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f71e'),
  description: 'do the laundry',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:18:46.771Z,
  priority: 'Medium'
}
{
  _id: ObjectId('68373f0c44e821fa6897f721'),
  description: 'climb the mountain',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}
{
  _id: ObjectId('683746d544e821fa6897f723'),
  description: 'charge my phone',
  completed: false,
  CreatedOn: 2025-05-28T17:24:37.983Z,
  UpdatedOn: 2025-05-28T17:50:47.418Z,
  priority: 'High',
  status: true
}
{
  _id: ObjectId('68373f0c44e821fa6897f71f'),
  description: 'brush your teeth',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium'
}


**Adding Due Date**
db.todo_list.updateMany({}, {$set: {DueDate: new Date()}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 10,
  modifiedCount: 10,
  upsertedCount: 0
}


**find all the records with a particular greater than or less than date.
(how you use multiple conditional operators)
try to find the tasks which are due today.**
	
db.todo_list.find(
	{DueDate: {
		$gte: ISODate("2025-05-28T00:00:00.000Z"),
		$lt: ISODate("2025-05-28T23:59:59.999Z")
	}
})
{
  _id: ObjectId('68373bf644e821fa6897f719'),
  description: 'iron clothes',
  CreatedOn: 2025-05-28T16:41:18.662Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium',
  DueDate: 2025-05-28T18:11:50.607Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f71a'),
  description: 'have dinner',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:16:40.131Z,
  priority: 'Medium',
  DueDate: 2025-05-28T18:11:50.607Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f71b'),
  description: 'eat laddoo',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:17:45.163Z,
  priority: 'Medium',
  DueDate: 2025-05-28T18:11:50.607Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f71c'),
  description: 'eat breakfast',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium',
  DueDate: 2025-05-28T18:11:50.607Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f71e'),
  description: 'do the laundry',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:18:46.771Z,
  priority: 'Medium',
  DueDate: 2025-05-28T18:11:50.607Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f71f'),
  description: 'brush your teeth',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium',
  DueDate: 2025-05-28T18:11:50.607Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f720'),
  description: 'drink water',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: true,
  UpdateOn: 2025-05-28T17:19:18.611Z,
  priority: 'Medium',
  DueDate: 2025-05-28T18:11:50.607Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f721'),
  description: 'climb the mountain',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium',
  DueDate: 2025-05-28T18:11:50.607Z
}
{
  _id: ObjectId('68373f0c44e821fa6897f722'),
  description: 'fly in the sky',
  CreatedOn: 2025-05-28T16:51:24.178Z,
  completed: false,
  UpdateOn: 2025-05-28T17:12:59.540Z,
  priority: 'Medium',
  DueDate: 2025-05-28T18:11:50.607Z
}
{
  _id: ObjectId('683746d544e821fa6897f723'),
  description: 'charge my phone',
  completed: false,
  CreatedOn: 2025-05-28T17:24:37.983Z,
  UpdatedOn: 2025-05-28T17:50:47.418Z,
  priority: 'High',
  status: true,
  DueDate: 2025-05-28T18:11:50.607Z
}



db.todo_list.insertOne({description: "check mails", completed: false, CreatedOn: new Date(), UpdatedOn: new Date(), priority: "High", DueDate: new Date()})
{
  acknowledged: true,
  insertedId: ObjectId('6837562344e821fa6897f724')
}


**Records created in less than 20 minutes ago**
const twentyMinutesAgo = new Date(Date.now() - 20 * 60 * 1000)
db.todo_list.find({
CreatedOn: {$gte: twentyMinutesAgo}
})
{
  _id: ObjectId('6837562344e821fa6897f724'),
  description: 'check mails',
  completed: false,
  CreatedOn: 2025-05-28T18:29:55.082Z,
  UpdatedOn: 2025-05-28T18:29:55.082Z,
  priority: 'High',
  DueDate: 2025-05-28T18:29:55.082Z
}


	

	  </pre>
