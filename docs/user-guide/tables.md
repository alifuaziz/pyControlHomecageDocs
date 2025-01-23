
## Tables information

### Mouse table

- Description: This table contains information about all mice currentl running in the system
- Headings: ['','Mouse_ID', 'RFID', 'Sex', 'Age', 'Experiment', 'Task','Protocol', 'User',
                            'Start_date', 'Current_weight', 'Start_weight', 'is_training',
                            'is_assigned', 'training_log', 'Setup_ID']

In the data/tasks directory, there are tasks (as .py files)
These tasks are implemented as statemachines.
The mouse table will have a task associated with it.
The task has variables that are associated with it that are set during the initialisation of the task

- Variables for `mouse_df` include the following:
  - `Persistant Variable`
  - `Summary Variables`
  - `set Variables`

### Experiment table

- Description: Table for system tab that shows all experiments currently running
- Headings: ['Select', 'Name', 'Setups', 'User', 'Active', 'Protocol', 'Subjects','n_subjects']

- Experiement overview tab functions:
- Seems like it is a lot of keeping the table clean...
- The functions are manipulating the dataframe tables to change them to be updated with the state that the user wants them to be.
  - (separation between data and logic is being done here)
  - 2 important functions: restart and stop an experiement.
    - Experiment Status:
      - restart_experiment sets the experiment status to True (active).
      - stop_experiment sets the experiment status to False (inactive).
      Mice Status:

      - restart_experiment assigns the mice to the experiment (assigned=True).
      - stop_experiment unassigns the mice from the experiment (assigned=False).
      Setups Status:

      - restart_experiment associates the setups with the experiment.
      - stop_experiment disassociates the setups from the experiment (experiment=None).

### Protocal Tables

- Descriptions:  
- ['Stage', 'Task', 'Tracked', 'Threshold(s)', 'Default(s)', 'Delete']

### variable table

- Description: Table that tracks what variables a mouse currently running in a task has
- Headings: ['Variable', 'Subject', 'Value', 'Persistent', 'Summary', 'Set', '']

### cage table

- Description:  This table contains information about the setups current
- Heading names:

- This contains the logic for the connect (to pyboard) function. (this is the first meaningful bug i am getting during trying to setup the board. )
-

### Connected_board