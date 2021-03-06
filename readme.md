# ProgressBar

Python class for creating and print ProgressBar.

### Prerequisites

Developed and tested in Linux and Python 3.6


### Installing

    pip3 install ebx_progressbar

or from source:

    python3 -m pip install [your_path]/ebx_progressbar/


## Functions

### Creating a object / instance
progressBar(fixed_width = 0, pos_Line = 0, pos_Column = 0, ind_NewLine = False)\

**Description**: Init class with max Size(fixed_width) Line (pos_Line) and Column (pos_Column) to show progress bar, and ind_NewLine that show all status update in same line (False) or in new line (True)

---

### print_Running

print_Running(int_Progress = 0, str_AdditionalText = '', pre_Text = '', ind_Simple = False)

**Description**: Progress with running format [|], [/], [-], [\], [|], [/], [-], [-], [|]

|Parameter|Description|
|---|---|
|**int_Progress**:|incremental value to progress| 
|**str_AdditionalText**:|Print text on the end of progressbar|
|**pre_Text**:|Print text on the beginning of progressbar|
|**ind_Simple**:|True shows additional time elapsed: Ex.: [Elapsed Time: 0:00:01]|

Call this function adding the value of int_Progress to progress

Return: None

Example of pre_Text and AdditionalText:\
```pre_Text: [-] AdditionalText```

---


### print_Bar

print_Bar(int_Progress = 0, pre_Text = ''):\

Description: Progress with common format: \
```pre_Text [Elapsed Time: 0:00:04] [####################################                                                        ] (40%)```


|Parameter|Description|
|---|---|
|**int_Progress**:|incremental value to progress until 100 (100%)|
|**pre_Text**:|Print text on the beginning of progressbar|


Call this function adding the value of int_Progress to progress

Return: None

---

## Examples of use

```
import ebx_progressbar

import time

lst_Files = ['song.odt', 'want.csv', 'information.js', 'green.gif']

##############################################################################
# Example 1:

print("\033c")
obj_ProgressBar = ebx_progressbar.progressBar(ind_NewLine=False)
for satr_File in lst_Files:
    for i in range(0, 101, 10):
        obj_ProgressBar.print_Running(i, str_AdditionalText='Logging ', pre_Text='File: ' + satr_File + ' ',
                                      ind_Simple=True)
        time.sleep(1)
    print('\r')


# Example 2:
print("\033c")
obj_ProgressBar = ebx_progressbar.progressBar(pos_Line=10, pos_Column=50, ind_NewLine=False)
for satr_File in lst_Files:
    for i in range(0, 101, 1):
        obj_ProgressBar.print_Running(i, str_AdditionalText='Logging ', pre_Text='File: ' + satr_File + ' ',
                                      ind_Simple=True)
        time.sleep(1)
    print('\r')


# Example 3:
print("\033c")
obj_ProgressBar = ebx_progressbar.progressBar(ind_NewLine=True)
for satr_File in lst_Files:
    for i in range(0, 101, 1):
        obj_ProgressBar.print_Running(i, str_AdditionalText='Logging ', pre_Text='File: ' + satr_File + ' ',
                                      ind_Simple=True)
        time.sleep(1)
    print('\r')

# Example 4:
print("\033c")
obj_ProgressBar = ebx_progressbar.progressBar(pos_Line=10, pos_Column=50, ind_NewLine=False)
for satr_File in lst_Files:
    for i in range(0, 101, 1):
        obj_ProgressBar.print_Running(i, str_AdditionalText='Logging ', pre_Text='File: ' + satr_File + ' ',
                                      ind_Simple=False)
        time.sleep(1)
    print('\r')

##############################################################################
# Example 5:
print("\033c")
obj_ProgressBar = ebx_progressbar.progressBar()
for satr_File in lst_Files:
    for i in range(0, 101, 10):
        obj_ProgressBar.print_Bar(i, pre_Text='File: ' + satr_File)
        time.sleep(1)
    print('\r')
    obj_ProgressBar.reset()

##############################################################################
# Example 6:

print("\033c")
obj_ProgressBar = ebx_progressbar.progressBar(100, 30, 1, ind_NewLine=False)
for satr_File in lst_Files:
    for i in range(0, 101, 10):
        obj_ProgressBar.print_Bar(i, pre_Text='File: ' + satr_File + ' ')
        time.sleep(1)
    print('\r')

# Example 7:
print("\033c")
obj_ProgressBar = ebx_progressbar.progressBar(200, 30, 1, ind_NewLine=True)
for satr_File in lst_Files:
    print('File: ' + satr_File + ' ')
    for i in range(0, 101, 10):
        obj_ProgressBar.print_Bar(i)
        time.sleep(1)
    print('\r')


# Example 8:
print("\033c")
obj_ProgressBar = ebx_progressbar.progressBar(ind_NewLine=True)
for satr_File in lst_Files:
    for i in range(0, 101, 10):
        obj_ProgressBar.print_Bar(i, pre_Text='File: ' + satr_File)
        time.sleep(1)
    print('\r')
    obj_ProgressBar.reset()
```


## Versioning
```
=======================================================================================
== Log Changes:
== Date:            2015-05-13
== Author:          Fausto Branco
== Version:         1.0.0
== Description:     Initial Version
=======================================================================================
```

## License



