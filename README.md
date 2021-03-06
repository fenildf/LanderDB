Usage
=====

    import landerdb
    db = landerdb.Connect("database") #Connects to the db "database", and in this case creates it

    db.insert("Table", {"key1":"value1"}, {"key2":"value2"}) #Inserts into the table "Table"
    db.save() #Saves the db file

    db.insert("Table2", {"key3":"value3", "key4":"value4"}) #Inserts into the table Table2
    db.save() #Saves the db file

    db.find("Table2", {"key3":"value3"})
    #returns [{"key3":"value3", "key4":"value4"}]

    db.get("Table", "key1") #Returns ["value1"]

    db.get("Table", all_=True) #Returns [{"key1":"value1"}, {"key2":"value2"}]

    db.remove("Table", {"key1":"value1"}) #Removes entry from table

    db.update("Table", {"key2":"value2"}, {"key5":"value5"}) #Table "Table" now contains only {"key5":"value5"} (replacing the previous entry)

    db.save() #Saves the db file

Same usage with autosave enabled


    import landerdb
    db = landerdb.Connect("database", autosave = True) #Connects to the db "database", and in this case creates it
    db.insert("Table", {"key1":"value1"}, {"key2":"value2"}) #Inserts into the table "Table"
    db.insert("Table2", {"key3":"value3", "key4":"value4"}) #Inserts into the table Table2
    db.find("Table2", {"key3":"value3"})
    #returns [{"key3":"value3", "key4":"value4"}]
    db.get("Table", "key1") #Returns ["value1"]
    db.get("Table", all_=True) #Returns [{"key1":"value1"}, {"key2":"value2"}]
    db.remove("Table", {"key1":"value1"}) #Removes entry from table
    db.update("Table", {"key2":"value2"}, {"key5":"value5"}) #Table "Table" now contains only {"key5":"value5"} (replacing the previous entry)

