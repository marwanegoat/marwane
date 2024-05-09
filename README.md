# marwane
code calculator in phyton
#les bibliotheque
from tkinter import *
from tkinter import ttk

calc = Tk() # understand OPP (Objects...)
calc.title("calculator")

def insert(text):
    if text != "=":
        marwane.insert("end", text)
    else:
        #المحاولة الصحيحة
        try: #exceptions handling 
            operation = eval(marwane.get())
            marwane.delete(0, "end")
            marwane.insert(0, "{}".format(operation))
        #المحاولة الغالطة
        except:
            marwane.delete(0, "end")
            marwane.insert(0, "error")
#design des bouttons
#function
def botton(text, clmn, rw):
    ttk.Button(calc, text=text, command=lambda: insert(text)).grid(column=clmn, row=rw, ipady=6, ipadx=1)
#size 15
marwane = ttk.Entry(calc, font="arial 15")
marwane.grid(column=0, row=0, columnspan=3, ipadx=4, ipady=8)
#les bouttons
botton("1", 0, 1)
botton("2", 1, 1)
botton("3", 2, 1)

botton("4", 0, 2)
botton("5", 1, 2)
botton("6", 2, 2)

botton("7", 0, 3)
botton("8", 1, 3)
botton("9", 2, 3)

botton("+", 0, 4)
botton("-", 1, 4)
botton("*", 2, 4)

botton("/", 0, 5)
botton(".", 1, 5)
botton("=", 2, 5)

botton("0", 1, 6)

calc.mainloop() #3lach ? 3lach ila makntch makykhdem walo ()
