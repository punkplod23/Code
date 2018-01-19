# Tkinter
- What is Tkinter?
  - Tkinter is Python's de-facto standard GUI (Graphical User Interface) package.
- What is a GUI
  - Graphical User interface
  - Users do not want to run things through command line to get things working 
      - They want
         - Click into windowed frames 
         - Click buttons
         - To look pretty
  
# How to install Tkinter
- Open up terminal (Ctrl+Alt+t)
  - sudo pip install python-tk
  - sudo apt-get install python3-tk
- Congratulations you have install Tkinter

# Lets create a tkinter window.
1. Open up your python Editor (Idle 3) 
```python
import tkinter as tk
from tkinter import *
from tkinter import ttk
from tkinter import messagebox
```
2. Lets Create a Class add some methods and then invoke it
```python
import tkinter as tk
from tkinter import *
from tkinter import ttk
from tkinter import messagebox


# Create class with constructer method
class Demo(Frame):

    # Constructor Method
    def __init__(self):
        self.createWindow()

    # Create window a New window
    def new_window(self):
        self.newWindow = Demo()

    # Invoke Tkinter
    def createWindow(self):
        tk.Frame.__init__(self)
   
    # Invoke Window
    def invokeWindow(self):
        self.pack()
        self.mainloop()

Demo()
```

3. Run the above code did you see a window popup?
  - Pointless was'nt it?
  - Lets do something fun.

4. Lets add (Width, Height, Background Color) Look at the differences between the two pieces of code.
  - Play with width,height and color
```python
import tkinter as tk
from tkinter import *
from tkinter import ttk
from tkinter import messagebox


# Create class with constructer method
class Demo(Frame):

    window_frame_width = 600
    window_frame_height = 800
    window_frame_color = "black"

    # Constructor Method
    def __init__(self):
        self.createWindow()

    # Invoke Tkinter
    def createWindow(self):
        tk.Frame.__init__(self,width=self.window_frame_width,height=self.window_frame_height,background=self.window_frame_color)
        self.invokeWindow()

    def invokeWindow(self):
        self.pack()
        self.mainloop()

Demo()
```
5. Lets Add some inputs a user can enter and a results method (Run The program)
```python
import io
import tkinter as tk
from tkinter import *
from tkinter import ttk
from tkinter import messagebox


# Create class with constructer method
class Demo(Frame):

    window_frame_width = 600
    window_frame_height = 800
    window_frame_color = "black"
    window_row = 0
    window_name = "My First Tkinter Program"

    # Constructor Method
    def __init__(self):
        self.createWindow()

    # Invoke Tkinter
    def createWindow(self):
        tk.Frame.__init__(self,width=self.window_frame_width,height=self.window_frame_height,background=self.window_frame_color)
        self.master.title(self.window_name)
        self.createInputs()
        self.invokeWindow()

    def createAddressFeilds(self,row):
        self.address_line1_label = Label(self, text="Address Line 1").grid(row=row,sticky='we')
        self.address_line1_input = StringVar()
        Entry(self,textvariable=self.address_line1_input).grid(row=row, column=1,sticky='we')
        row = row+1
        self.address_line2_label = Label(self, text="Address Line 2").grid(row=row,sticky='we')
        self.address_line2_input = StringVar()
        Entry(self,textvariable=self.address_line2_input).grid(row=row, column=1,sticky='we')
        row = row+1
        self.address_line3_label = Label(self, text="Address Line 3").grid(row=row,sticky='we')
        self.address_line3_input = StringVar()
        Entry(self,textvariable=self.address_line3_input).grid(row=row, column=1,sticky='we')
        row = row+1
        self.address_line4_label = Label(self, text="Address Line 4").grid(row=row,sticky='we')
        self.address_line4_input = StringVar()
        Entry(self,textvariable=self.address_line4_input).grid(row=row, column=1,sticky='we')
        row = row+1
        self.postcode_label = Label(self, text="Postcode").grid(row=row,sticky='we')
        self.postcode_input = StringVar()
        Entry(self,textvariable=self.postcode_input).grid(row=row, column=1,sticky='we')
        row = row + 1
        return row

    def createInputs(self):

        # Name Input with label
        self.name_label = Label(self, text="Name").grid(row=0,sticky='we')
        self.name_input = StringVar()
        Entry(self, textvariable=self.name_input,width=int(self.window_frame_width*0.10)).grid(row=0, column=1,sticky='we')

        #Age input with Label
        self.age_label = Label(self, text="Age").grid(row=1,sticky='we')
        self.age_input = StringVar()
        Entry(self, textvariable=self.age_input).grid(row=1, column=1,sticky='we')

        # I Like input with Label
        self.i_like_label = Label(self, text="I Like").grid(row=2,sticky='we')
        self.i_like_input = StringVar()
        Entry(self, textvariable=self.i_like_input).grid(row=2, column=1,sticky='we')

        # Quote I Like
        self.quote_i_like_label = Label(self, text="Quote I Like").grid(row=3,sticky='we')
        self.quote_i_like_input = StringVar()
        Entry(self, textvariable=self.quote_i_like_input).grid(row=3, column=1,sticky='we')

        #Dynamically create address Feilds
        row = self.createAddressFeilds(4)
        # Button
        self.submit_button = Button(self, text="Submit", command=self.displayResults).grid(row=row,column=0,columnspan=2,sticky='we')


    def displayResults(self):
        tk.Frame.__init__(self, width=self.window_frame_width, height=self.window_frame_height,background=self.window_frame_color)
        self.master.title(self.window_name)
        self.invokeWindow()

    def invokeWindow(self):
        self.grid(sticky="we")
        self.grid_columnconfigure(0, weight=1)
        self.grid_columnconfigure(1, weight=1)
        self.pack(side="bottom", fill="both", expand=True)
        #self.pack()
        self.mainloop()

Demo()
```

6. OK lets go through some class basics from the code above now?
  - self. refers to anything in the class.
  - in this case we are loading the whole of tkinter library into the class
  - inside the class we have this variable window_name 
    - Change this re-run the python script.
  - In the createWindow Method
    - When a function (def) in python lives inside a class we call it a method rather than a function.
    - ON this line ```python self.master.title(self.window_name)```
    - Replace the self.window_name with a string like this ```python self.master.title("Test Program")```


  

