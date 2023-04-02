# Text_Editor_in_Python
## About Text Editor
Text Editor is a simple application that helps a user to write texts and save it in a file. It is a basic beginners project but very interesting to make. So let’s get started.

# Project Details
This is a very interesting project using Python. Here we are going to create a text editor which will have several options like copy, paste, save, save as etc. We will try to include every possible option in it. While creating the project we will be using these modules and libraries –

* Tkinter Module
* Filedialog

# Steps to Create Text Editor Using Python
1. Importing libraries:
# Import required modules and liberaries
from tkinter import *
import tkinter as tk
from tkinter.filedialog import asksaveasfilename
from tkinter import * for creating GUI in Python.
Fileddialog – Inbuilt function for creating files in Python. We have imported asksaveasfilename to create a save file option in our text editor.
2. Create the main window:
stimulator_window = Tk()
stimulator_window.geometry('600x600')
stimulator_window.title('TechVidvan')

heading = Label(stimulator_window,text='Welcome to the Text Editor',font=('bold',20),bg='light grey') # This will create a label for the heading.
heading.pack() # You have to pack this label so that it can be seen in the window
Creating the main window with scrollbar and save button.
Stimulator_window = Tk() – to create the main window.
title() – for giving the title to the window created.
geometry()- for giving the dimensions to the window created.
We want to give a heading to our window so we create a head variable and assign it with a Label. This label will display the desired text with attributes like font, colour, size etc. To place this head variable on the window we use the pack() function.Pack() function helps us display the label created.
3. Creating the Text Area, Scrollbar and Button:
Advertisement

scrollbar = Scrollbar(stimulator_window).pack(side=RIGHT,fill=Y)
Editor=Text(stimulator_window,width=400,height=450,yscrollcommand=scrollbar.set).pack(fill=BOTH)
scrollbar.config(command=Editor.yview)
Text()- to create a text area in the window and pack it using pack(). This text area is the main area in which we will be writing our documents.
We add a scrollbar to our text area using the Scrollbar() function which is an inbuilt function. While packing the scroll bar, we pack it on the RIGHT side so that it is vertical. It is compulsory to configure the scrollbar using the config() method. Yview specifies that the scrollbar is for the vertical section of the text area.
button = Button(stimulator_window,text='Save',font=('normal',10),command=save, bg='yellow')
button.place(x=270,y=520)
We want a save option in our text editor. To enable this save option, we create a save button using the Button() method which is an inbuilt method of the Tkinter Module. Command= save means that whenever the button is clicked, it will initiate the save() function(save function is given below in the article). To display the save button on the window, we use the place() method. While using the place() method, it is compulsory to specify the x and y coordinates respective to the window.
4. Save() Function:
def save():
 filepath = asksaveasfilename(defaultextension="txt",filetypes=[("Text Files", "*.txt"), ("All Files", "*.*")])
 if not filepath:
  return
  with open(filepath, "w") as output_file:
   text = Editor.get(1.0, tk.END)
   output_file.write(text)
 stimulator_window.title(f"Entitled - {filepath}")
We want to save our file that we make in the text editor for which we make a save button. Now let us make a function that will let the saving of a file happen.
Asksaveasfilename() – this method is a part of filedialog library. This function helps us to set what the default type of file will be in the path. It basically lets us decide what the path and extension will be.
If no filepath is given then return back. If the file path and name is given it opens the file using the open() method and we write all the text written in the text editor one by one using the write() method. After the file is saved, we display the filename and path on the window as the window title.
5. Main command:
Advertisement

# command to run
window.mainloop()
Through mainloop() we command to display the window and display the output of the project.
