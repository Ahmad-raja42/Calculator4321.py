# Calculator4321.py

# importing tkinter
import tkinter as tk

#lets see the what is inside tkinter module
#print(dir(tk))

#lets create the base GUI
root = tk.Tk()

# lets create the test function
def test(event):
    buttonpressed = event.widget.cget('text')
    if buttonpressed == '=':
        expression = label.cget('text')
        result = eval(expression)
        label.config(text=result)
    elif buttonpressed in ["CE", "C", "X"]:
        label.config(text='')
    else:
        label_text = str(label.cget('text'))
        if label_text == '0':
            label.config(text=buttonpressed)
        else:
            label_text += buttonpressed
            label.config(text=label_text)
#GUI Properties
# Size change
root.geometry("320x480")
root.resizable(width=False, height=False) #fixed size
root.title('Calculator') # Title Change
root.iconbitmap('Calculator.ico')
root.config(bg ='#FFFDD0') # giving a bg color to root gui

# adding widget now
# label widget to display text
label = tk.Label(root, text ='0', bg ='#FFFDD0', font = ('comic sans MS', 30), anchor = 'e', padx = 10)
label.pack(pady = (65, 10), fill = 'x')

# lets add a container in root gui
frame = tk.Frame(root, bg='#FFFDD0')
frame.pack(fill='both')

# button --> row 0 --> percentage, CE, C, Delete
btn_percent = tk.Button(frame, text='%', width=9, height=3, bg='#ffffff', relief='groove', font=('trebuchet',9))
btn_ce = tk.Button(frame, text='CE',width=9,height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_c = tk.Button(frame, text='C',width=9,height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_delete = tk.Button(frame, text='X',width=9,height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_percent.grid(row = 0, column = 0,padx=3,pady=3)
btn_ce.grid(row = 0, column = 1,padx=3,pady=3)
btn_c.grid(row = 0, column = 2,padx=3,pady=3)
btn_delete.grid(row = 0, column = 3,padx=3,pady=3)

# lets bind the left click event over buttons
btn_percent.bind('<Button-1>',test)
btn_ce.bind('<Button-1>',test)
btn_c.bind('<Button-1>',test)
btn_delete.bind('<Button-1>',test)

# button --> row 1 --> 7, 8, 9, *
btn_seven = tk.Button(frame, text='7',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_eight = tk.Button(frame, text='8',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_nine = tk.Button(frame, text='9',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_mult = tk.Button(frame, text='*',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_seven.grid(row = 1, column = 0,padx=3,pady=3)
btn_eight.grid(row = 1, column = 1,padx=3,pady=3)
btn_nine.grid(row = 1, column = 2,padx=3,pady=3)
btn_mult.grid(row = 1, column = 3,padx=3,pady=3)

# lets bind the left click event over buttons
btn_seven.bind('<Button-1>',test)
btn_eight.bind('<Button-1>',test)
btn_nine.bind('<Button-1>',test)
btn_mult.bind('<Button-1>',test)

#button --> row 2 --> 4, 5, 6, -
btn_four = tk.Button(frame, text='4',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_five = tk.Button(frame, text='5',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_six = tk.Button(frame, text='6',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_sub = tk.Button(frame, text='-',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_four.grid(row = 2, column = 0,padx=3,pady=3)
btn_five.grid(row = 2, column = 1,padx=3,pady=3)
btn_six.grid(row = 2, column = 2,padx=3,pady=3)
btn_sub.grid(row = 2, column = 3,padx=3,pady=3)

# lets bind the left click event over buttons
btn_four.bind('<Button-1>',test)
btn_five.bind('<Button-1>',test)
btn_six.bind('<Button-1>',test)
btn_sub.bind('<Button-1>',test)

#button --> row 3 --> 1, 2, 3, +
btn_one = tk.Button(frame, text='1',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_two = tk.Button(frame, text='2',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_three = tk.Button(frame, text='3',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_plus = tk.Button(frame, text='+',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_one.grid(row = 3, column = 0,padx=3,pady=3)
btn_two.grid(row = 3, column = 1,padx=3,pady=3)
btn_three.grid(row = 3, column = 2,padx=3,pady=3)
btn_plus.grid(row = 3, column = 3,padx=3,pady=3)

# lets bind the left click event over buttons
btn_one.bind('<Button-1>',test)
btn_two.bind('<Button-1>',test)
btn_three.bind('<Button-1>',test)
btn_plus.bind('<Button-1>',test)

#button --> row 4 --> =, 0, ., /
btn_equal = tk.Button(frame, text='=',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_zero = tk.Button(frame, text='0',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_decimal = tk.Button(frame, text='.',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_divide = tk.Button(frame, text='/',width=9, height=3, bg='#ffffff',relief='groove', font=('trebuchet',9))
btn_equal.grid(row = 4, column = 0,padx=3,pady=3)
btn_zero.grid(row = 4, column = 1,padx=3,pady=3)
btn_decimal.grid(row = 4, column = 2,padx=3,pady=3)
btn_divide.grid(row = 4, column = 3,padx=3,pady=3)

# lets bind the left click event over buttons
btn_equal.bind('<Button-1>',test)
btn_zero.bind('<Button-1>',test)
btn_decimal.bind('<Button-1>',test)
btn_divide.bind('<Button-1>',test)

#lets run mainloop
root.mainloop()
