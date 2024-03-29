# alu-AirBnB_clone

Enterprise Web-Development

![hbnb_logo](https://github.com/Williedaniels/alu-AirBnB_clone/assets/125483758/4d09e883-3934-4f8e-86a1-a495a34bb34a)

<h1 (align="center")>Alu-AirBnB</h1>
<p [align="center"]>An AirBnB clone</p>

---

## Description :house:

HBnB is a comprehensive web app, mirroring AirBnB, with features like database storage, a back-end API, and front-end interactions. It's the initial stage in creating a complete web application: an AirBnB replica. This stage includes a unique command-line interface for managing data and the foundational classes for storing it.

## Usage :computer:

The console works both in interactive mode and non-interactive mode, much like a Unix shell.
It prints a prompt **(hbnb)** and waits for the user for input.

Command | Example
------- | -------
Run the console | ```./console.py```
Quit the console | ```(hbnb) quit```
Display the help for a command | ```(hbnb) help <command>```
Create an object (prints its id)| ```(hbnb) create <class>```
Show an object | ```(hbnb) show <class> <id>``` or ```(hbnb) <class>.show(<id>)```
Destroy an object | ```(hbnb) destroy <class> <id>``` or ```(hbnb) <class>.destroy(<id>)```
Show all objects, or all instances of a class | ```(hbnb) all``` or ```(hbnb) all <class>```
Update an attribute of an object | ```(hbnb) update <class> <id> <attribute name> "<attribute value>"``` or ```(hbnb) <class>.update(<id>, <attribute name>, "<attribute value>")```

Non-interactive mode example

```bash
$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  all  count  create  destroy  help  quit  show  update
```

## Models :penguin:

The folder [models](./models/) contains all the classes used in this project.

File | Description | Attributes
---- | ----------- | ----------
[base_model.py](./models/base_model.py) | BaseModel class for all the other classes | id, created_at, updated_at
[user.py](./models/user.py) | User class for future user information | email, password, first_name, last_name
[amenity.py](./models/amenity.py) | Amenity class for future amenity information | name
[city.py](./models/city.py) | City class for future location information | state_id, name
[state.py](./models/state.py) | State class for future location information | name
[place.py](./models/place.py) | Place class for future accomodation information | city_id, user_id, name, description, number_rooms, number_bathrooms, max_guest, price_by_night, latitude, longitude, amenity_ids
[review.py](./models/review.py) | Review class for future user/host review information | place_id, user_id, text

## File storage :baggage_claim:

The folder [engine](./models/engine/) manages the serialization and deserialization of all the data, following a JSON format.

A FileStorage class is defined in [file_storage.py](./models/engine/file_storage.py) with methods to follow this flow:
```<object> -> to_dict() -> <dictionary> -> JSON dump -> <json string> -> FILE -> <json string> -> JSON load -> <dictionary> -> <object>```

The [**init**.py](./models/__init__.py) file contains the instantiation of the FileStorage class called **storage**, followed by a call to the method reload() on that instance.
This allows the storage to be reloaded automatically at initialization, which recovers the serialized data.

## Tests :straight_ruler:

Every bit of code gets checked using the **unittest** module.
You'll find the class tests in the [tests](./tests) folder.
If you want to run all tests at once, use the command below:

```text
python3 unittest -m discover tests
```

Or, you could choose to run just one test file at a time:

```text
python3 unittest -m tests/test_console.py
```

## Authors :black_nib:

* **Willie Bless Daniels** <[Williedaniels](https://github.com/Williedaniels)> <w.daniels@alustudent.com>
* **Diane Ingabire** <[] ()> <d.ingabire1@alustudent.com>
