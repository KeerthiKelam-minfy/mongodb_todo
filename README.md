# mongodb_todo
<pre> \`\`\`
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
db.todo_list.updateOne({
description: "iron clothes", CreatedOn: new Date()})
MongoInvalidArgumentError: Update document requires atomic operators
db.todo_list.updateOne({
description: "iron clothes"}, {CreatedOn: new Date()})
MongoInvalidArgumentError: Update document requires atomic operators
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
db.todo_list.insertMany({status: "done", description: "have dinner", CreatedOn: new Date()},
                        {status: "done", description: "eat laddoo", CreatedOn: new Date()},
												{status: "pending", description: "eat breakfast", CreatedOn: new Date()},
                        {status: "pending", description: "finish assignment", CreatedOn: new Date()},
                        {status: "done", description: "do the laundry", CreatedOn: new Date()},
                        {status: "pending", description: "brush your teeth", CreatedOn: new Date()},
                        {status: "done", description: "drink water", CreatedOn: new Date()},
                        {status: "pending", description: "climb the mountain", CreatedOn: new Date()},
                        {status: "pending", description: "fly in the sky", CreatedOn: new Date()}
)
MongoInvalidArgumentError: Argument "docs" must be an array of documents
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

	 \`\`\` </pre>
