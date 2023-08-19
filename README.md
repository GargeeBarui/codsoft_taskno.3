from tkinter import *
import string
import random
def generate():
    small = 'abcdefghijklmnopqrstuvwxyz'
    cap   = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
    numbers = '123456789'
    symbols = '#$%&*@!'
    all = small+cap+numbers+symbols
    password_length= int(length_Box.get())

    password = random.sample(all,password_length)
    pwdField.insert(0,password)
root = Tk()
root.config(bg='red')
root.geometry("225x150")
choice = IntVar()
Font = ('arial',10,'bold')
passwordLabel = Label(root,text = "Password Generator", font = ("arial narrow",20,'bold'))
passwordLabel.grid(pady = 1)


lengthlabel = Label(root,text = 'length',font = ("arial narrow",10,'bold'))
lengthlabel.grid(pady = 1)
length_Box = Spinbox(root,from_=8,to_=12,width = 5,font = Font)
length_Box.grid(pady = 1)
generateButton = Button(root,text = "Generate",font= Font,command = generate)
generateButton.grid(pady = 1)
pwdField = Entry(root,width = 20,bd= 1,font = Font)
pwdField.grid(pady = 1)


root.mainloop()
