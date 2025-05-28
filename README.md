# mongodb_todo


db.todo_list.insertOne({status: "done", description: "drink water", timestamp: new Date()})  
{  
  acknowledged: true,  
  insertedId: ObjectId('6837300e2680a6047257ac46')  
}  
db.todo_list.insertMany([{status: "pending", description: "do the assignment", timestamp: new Date()},
                        {status: "done", description: "check mails", timestamp: new Date()}, 
                        {status: "done", description: "pack your bag", timestamp: new Date()},
                        {status: "pending", description:"iron clothes", timestamp: new Date(), 
												])

