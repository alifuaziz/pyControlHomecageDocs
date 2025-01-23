# Notes
>
> THE IDE I USED TO DEBUG IS THONNY It has pretty decent error messages yay!

Goals of this program:

- read and write the data from the behaviour to disk
- be able to upload the firmware to the micropython board
- have an interface for controlling the experiments that exist.

- Example useage
- def get_states(self):
        '''Return states as a dictionary {state_name: state_ID}'''
        return eval(self.exec('fw.get_states()').decode().strip())
  This is a running a function on the pycontrol board itself.

## How does the firmware communicate with the main script

- Pyboard info:
- Whilst it is running the main script i guess that it can't be read... And if the framework is uploaded successfully they it will run automatically and cause data be to continuously sent from the pyboard back to the main computer.
- ? how to read the output of the file

- the [com](/com) folder is the folder which does a lot the logic that is involved in taking the information from the pyb and writing it down to disk. (thus the logic of this program)
- A lot of the way the  gui interacts with the logic is by displaying it and adding the basic information (i.e. names / configurations of setups) to it.

## Structure

Each of the tables have a fill table method for populating the table from the db file
Refresh functions are present in lots of the classes for updating states.

All setups require two things:

- pycontrol board which handles the task
- access control which handles the access of the animal to the task

