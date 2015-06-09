MongoDB
=======

* Use command ::
    
    > use DATABASE_NAME

* Show databases :: 
    
    > show dbs

* Name database which is currently in use ::

    > db

* Inserting collection using insert ::

    > db.test.insert({ "name" : "Sample data" })

* Drop database ::
    
    > db.dropDatabase()

* CreateCollection Method ::
    
    > db.createCollection(name, options)

* Show collections method ::
    
    > show collections

* Dropping Collections ::
    
    > db.COLLECTION_NAME.drop()

* Saving collection data ::
    
    > db.COLLECTION_NAME.save(document)

* To query data from collection ::
    
    > db.COLLECTION_NAME.find()

* To display result in formatted way ::
    
    > db.COLLECTION_NAME.find().pretty()

* To query data from collection ::

    > db.COLLECTION_NAME.findOne()
    
* RDBMS like where clauses ::
    
    > db.COLLECTION_NAME.find({ "likes" : "my_value" })
    > db.COLLECTION_NAME.find({ "likes" : { $lt : "50"} })
    > db.COLLECTION_NAME.find({ "likes" : { $lte : "50"} })
    > db.COLLECTION_NAME.find({ "likes" : { $gt : "50"} })
    > db.COLLECTION_NAME.find({ "likes" : { $gte : "50"} })
    > db.COLLECTION_NAME.find({ "likes" : { $ne : "50"} })

* AND clause ::
    
    > db.COLLECTION_NAME.find({ "likes" : "50", "name" : "Sample" })

* OR clause ::
    
    > db.COLLECTION_NAME.find({ $or : [ {"likes" : "50"} , {"name" : "Sample"} ] })

* AND and OR together ::

    > db.COLLECTION_NAME.find({"name": "sample", $or : [ {"likes" : "50"} , {"name" : "Sample"} ] })

* Update ::
    
    > db.COLLECTION_NAME.update(SELECTION_CRITERIA, UPDATE_DATA)
    > db.mydata.update({'title' : 'sample' }, { $set : { 'title' : 'New Sample' } } )

* Remove ::
    
    > db.COLLECTION_NAME.remove({ 'title':  'sample' })

* Remove One::

    > db.COLLECTION_NAME.remove({ 'title':  'sample' }, 1)


