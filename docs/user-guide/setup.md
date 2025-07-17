## Example simulation of sending signals to the System controller

```python
sc = system_controller(AC=ac_board, PYC=pyc_board)

# Instead of directly setting up the task, use the RFID signal read from the Access control board to setup the task

sc.process_data_AC(new_data=["state:allow_entry"]) # Reset Mouse data
sc.process_data_AC(new_data=["weight:50"]) # Set Mouse data to 50gstate:
sc.process_data_AC(new_data=["RFID:116000039961"]) # Set RFID
sc.process_data_AC(new_data=["state:enter_training_chamber"])
sc.process_data_AC(new_data=["state:mouse_training"]) # Handle the mouse training
```

THis is useful for debugging

The pyControl board needs its hardware definition to start setting up the task properly

## pyControl Board needs Harwardware defintion to start tasks

This should be implemented automatically somehow?

- The user would be required to say what type of hardware is being used on this setup.
-
