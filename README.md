from tkinter import *
import math
import tkinter.messagebox
import random

root = Tk()
root.title("Scientific Calculator")
root.configure(background = "white")
root.resizable(0,0)
root.geometry("480x568+450+90")
calc = Frame(root)
calc.grid()

class Calc():

    def __init__(self):
        self.total=0
        self.current=''
        self.input_value=True
        self.check_sum=False
        self.op=''
        self.result=False
        

    def numberEnter(self,num):
        bgcol = random.sample(col,k=9)
        for i in range(9):
            btn[i].config(bg = bgcol[i])

        btns = [btnzero,btnAlloff,btnsq,btnadd,btnsub,btnMul,btndiv,btnDot,btnEquals,btnPM,btnClear]
        darkcol = list(dco.values())
        bgdark = random.sample(darkcol,k=11)
        for i,j in enumerate(btns):
            j.config(bg=bgdark[i])


        self.result=False
        firstnum=txtDisplay.get()
        secondnum=str(num)
        if self.input_value:
            self.current=secondnum
            self.input_value=False
        else:
            if secondnum ==".":
                if secondnum in firstnum:
                    return
            self.current = firstnum+secondnum
        self.display(self.current)

    def sum_of_total(self):
        self.result=True
        self.current=float(self.current)
        if self.check_sum==True:
            self.valid_function()    

        else:
            self.total=float(txtDisplay.get())
   
    def display(self,value):
        txtDisplay.delete(0,END)
        txtDisplay.insert(0,value)

    def valid_function(self) :
        try:

            if self.op == 'add':
                self.total += self.current
            if self.op =='sub':
                self.total -= self.current
            if self.op =="multi":
                self.total *= self.current
            if self.op == 'divide':
                self.total/= self.current
            if self.op == 'mod':
                self.total %= self.current 
    
        

        except ValueError:
            pass
        except NameError:
            pass
        except ValueError:
            pass
        except NameError:
            pass
        except ZeroDivisionError:
            pass           
            
        self.input_value=True
        self.check_sum= False
        self.display(self.total)
        
    def operation(self,op):
        try:
            self.current=float(self.current)
            if self.check_sum==True :           
                self.valid_function()       
            elif not self.result:
                self.total=self.current
                self.input_value=True
            self.check_sum=True
            self.op=op
            self.result=False
        except ValueError:
            pass
        except NameError:
            pass
        except ValueError:
            pass
        except NameError:
            pass
    
    def clear_Entry(self):
        txtDisplay.config(state=NORMAL)
        self.result = False
        self.current = "0"            
        self.display(0)
        self.input_value= True


    def All_OFF_Entry(self):
        txtDisplay.delete(0,END)
        txtDisplay.config(state=DISABLED)
       

    def pi(self):
        try:
            self.result
            self.current=math.pi
            self.display(self.current)
        except ValueError:
            pass
    def tau(self):
        try:
            self.result = False
            self.current = math.tau
            self.display(self.current)
        except ValueError:
            pass
    def e(self):
        try:
            self.result = False
            self.current = math.e
            self.display(self.current)
        except ValueError:
            pass
    def mathPM(self):
        try:
            self.result = False
            self.current = -(float(txtDisplay.get()))
            self.display(self.current)
        except ValueError:
            pass
    def squared(self):
        try:
            self.result = False
            self.current = math.sqrt(float(txtDisplay.get()))
            self.display(self.current)
        except ValueError:
            pass
    def cos(self):
        try:
            self.result = False
            self.current = math.cos(math.radians(float(txtDisplay.get())))
            self.display(self.current)
        except ValueError:
            pass

    def cosh(self):
        try:
            self.result = False
            self.current = math.cosh(math.radians(float(txtDisplay.get())))
            self.display(self.current)    
        except ValueError:
            pass
    def tan(self):
        try: 
            self.result = False
            self.current = math.tan(math.radians(float(txtDisplay.get())))
            self.display(self.current)
        except ValueError:
            pass
    def tanh(self):
        try:
            self.result = False
            self.current = math.tanh(math.radians(float(txtDisplay.get())))
            self.display(self.current)
        except ValueError:
            pass

    def sin(self):
        try:
            self.result = False
            self.current = math.sin(math.radians(float(txtDisplay.get())))
            self.display(self.current)
        except ValueError:
            pass
    def sinh(self):
        try:
            self.result = False
            self.current = math.sinh(math.radians(float(txtDisplay.get())))
            self.display(self.current)
        except ValueError:
            pass

    def log(self):
        try:
            self.result = False
            self.current = math.log(float(txtDisplay.get()))
            self.display(self.current)
        except ValueError:
            pass

    def exp(self):
        try:
            self.result = False
            self.current = math.exp(float(txtDisplay.get()))
            self.display(self.current)
        except ValueError:
            pass
    
    def Economyosh(self):
        try:
            self.result = False
            self.current = math.acosh(float(txtDisplay.get()))
            self.display(self.current)
        except ValueError:
            pass
    
    def asinh(self):
        try:
            self.result = False
            self.current = math.asinh(float(txtDisplay.get()))
            self.display(self.current)
        except ValueError:
            pass
    
    def expm1(self):
        try:
            self.result = False
            self.current = math.expm1(float(txtDisplay.get()))
            self.display(self.current)
        except ValueError:
            pass
    
    def lgamma(self):
        try:
            self.result = False
            self.current = math.lgamma(float(txtDisplay.get()))
            self.display(self.current)
        except ValueError:
            pass

    def degrees(self):
        try:
            self.result = False
            self.current = math.degrees(float(txtDisplay.get()))
            self.display(self.current)
        except ValueError:
            pass

    def log2(self):
        try:
            self.result = False
            self.current = math.log2(float(txtDisplay.get()))
            self.display(self.current)
        except ValueError:
            pass    

    def log10(self):
        try:
            self.result = False
            self.current = math.log10(float(txtDisplay.get()))
            self.display(self.current)
        except ValueError:
            pass    
    def log1p(self):
        try:
            self.result = False
            self.current = math.log1p(float(txtDisplay.get()))
            self.display(self.current)
        except ValueError:
            pass


added_value = Calc()

txtDisplay = Entry(calc,
                   font=('Hevetica',20,'bold'),
                   bg='grey',
                   fg='black',
                   bd=30,
                   
                   width=28,
                   justify=RIGHT)
txtDisplay.grid(row=0,
                column=0,
                columnspan=4,
                pady=1)

txtDisplay.insert(0,'0') 

numberpad = "789456123"

i = 0

btn = []
col = [
    "lightblue",
    "lightgreen",
    "lightyellow",
    "lightpink",
    "lightcoral",
    "lightcyan",
    "lightgoldenrodyellow",
    "lightgray",
    "lavender",
    "peachpuff",
    "honeydew",
    "mintcream",
    "seashell",
    "mistyrose",
    "lavenderblush",
    "lightsteelblue",
    "lightsalmon",
    "powderblue",
    "khaki",
]


# Define 20 dark colors
dco ={
    "Dark Blue": "#0A1F3D",
    "Dark Green": "#005B5C",
    "Dark Red": "#8B0000",
    "Dark Purple": "#4B0082",
    "Dark Teal": "#004D4D",
    "Dark Slate Gray": "#2F4F4F",
    "Charcoal": "#36454F",
    "Midnight Blue": "#191970",
    "Dark Olive Green": "#556B2F",
    "Indigo": "#4B0082",
    "Crimson": "#DC143C",
    "Dark Magenta": "#8B008B",
    "Deep Pink": "#FF1493",
    "Dark Salmon": "#E9967A",
    "Saddle Brown": "#8B4513",
    "Dark Orchid": "#9932CC",
    "Royal Blue": "#4169E1",
    "Forest Green": "#228B22",
    "Steel Blue": "#4682B4",
    "Dark Goldenrod": "#B8860B"
    }



for j in range(2,5):
    bgcol = random.choice(col)

    for k in range(3):
        btn.append(Button(calc,
                          width=6,
                          height=2,
                          bg='dark grey',
                          fg='black',
                          font=('Helvetica',20,'bold'),
                          bd=4,text=numberpad[i]))

        btn[i].grid(row=j,column=k,pady=1)

        btn[i]["command"] = lambda x=numberpad[i]: added_value.numberEnter(x)
        i += 1
        
btnClear = Button(calc, text=chr(67),width=6,
                  height=2,bg='grey',fg="white",
                  font=('Helevetica',20,'bold'),
                  bd=4,command=added_value.clear_Entry
                  )
btnClear.grid(row=1,column=1,pady=1)

btnAlloff = Button(calc,text=chr(111)+chr(102)+chr(102),
                     width=6,height=2,
                     bg='red',fg="white",
                     font=('Helvetica',20,'bold'),
                     bd=4,
                     command=added_value.All_OFF_Entry
                     )
btnAlloff.grid(row=1,column=0,pady=1)

btnsq = Button(calc,text='\u221A',width=6,height=2,
               bg='grey',fg="white",font=('Helvetica',20,'bold'),
               bd=4,command=added_value.squared
               )
btnsq.grid(row=1,column=2,pady=1)

btnadd = Button(calc,text='+',width=6,height=2,
                bg='grey',fg="white",
                font=('helvetica',20,'bold'),
                bd=4,command=lambda:added_value.operation("add")
                )
btnadd.grid(row=1,column=3,pady=1)

btnsub= Button(calc,text='-',width=6,height=2,bg='grey',fg="white",
               font=('helvetica',20,'bold'),
               bd=4,command=lambda:added_value.operation('sub')
               )
btnsub.grid(row=2,column=3,pady=1)

btnMul=Button(calc,text='*',width=6,height=2,
              bg='grey',fg="white",
              font=('Helvetica',20,'bold'),
              bd=4,command=lambda:added_value.operation('multi')
              )
btnMul.grid(row=3,column=3,pady=1)

btndiv=Button(calc,text='/',width=6,height=2,bg='grey',fg="white",
              font=('Halvetica',20,'bold'),
              bd=4,command=lambda:added_value.operation('divide')
              )
btndiv.grid(row=4,column=3,pady=1)

btnzero= Button(calc,text='0',width=6,height=2,bg='grey',fg="white",
                font=('Helvetica',20,'bold'),
                bd=4,activebackground = random.choice(col),command=lambda:added_value.numberEnter('0')
                )
btnzero.grid(row=5,column=0 ,pady=1)

btnDot=Button(calc,text='.',width=6,height=2,bg='grey',fg="white",
             font=('helvetica',20,'bold'),
             bd=4,command=lambda:added_value.numberEnter('.')
             )
btnDot.grid(row=5,column=1,pady=1)

btnPM=Button(calc,text=chr(177),width=6,height=2,bg='grey',fg="white",
             font=('helvetica',20,'bold'),
             bd=4,command=added_value.mathPM
             )
btnPM.grid(row=5,column=2,pady=1)

btnEquals = Button(calc,text='=',width=6,
                   height=2,bg='green',fg="white",
                   font=('helvetica',20,'bold'),
                   bd=4,command=added_value.sum_of_total
                   )
btnEquals.grid(row=5,column=3,pady=1)
# ROW 1 : 

btnpi = Button(calc,text='pi',width=6,
                   height=2,bg='grey',fg='black',
                   font=('helvetica',20,'bold'),
                   bd=4,command=added_value.pi
                   ).grid(row=1,column=4,pady=1)

btnCos = Button(calc, text="Cos",width=6,
                height=2,bg='grey',fg='black',
                font=('Helvetica',20,'bold'),
                bd=4,command=added_value.cos
               ).grid(row=1, column= 5, pady = 1)

btntan = Button(calc,text='tan',width=6,height=2,
                bg='grey',fg='black',font=('Helvetica',20,'bold'),
                bd=4,command=added_value.tan
                ).grid(row=1,column=6,pady=1)

btnsin = Button(calc,text='sin',width=6,height=2,
                bg='grey',fg='black',
                font=('Helvetica',20,'bold'),
                bd=4,command=added_value.sin
                ).grid(row=1,column=7,pady = 1)

#row 2 :

btn2pi=Button(calc,text='2pi',width=6,height=2,
              bg='grey',fg='black',
              font=('Helvetica',20,'bold'),
              bd=4,command=added_value.tau
              ).grid(row=2,column=4,pady=1)

btnEconomyosh=Button(calc,text='Cosh',width=6,height=2,
               bg='grey',fg='black',
               font=('Helvetica',20,'bold'),
               bd=4,command=added_value.cosh
               ).grid(row=2,column=5,pady=1)


btnatanh = Button(calc, text="tanh", width=6,
                 height=2, bg='grey', fg='black',
                 font=('Helvetica', 20, 'bold'),
                 bd=4, command=added_value.tanh
                 ).grid(row=2, column=6, pady=1)


btnasinh = Button(calc, text="sinh",width=6, 
                 height=2,bg='grey',fg='black',
                 font=('Helvetica',20,'bold'),
                 bd=4,command=added_value.sinh
                ).grid(row=2, column= 7, pady = 1)

#Row 3 :

btnlog= Button(calc,text='log',width=6,height=2,
               bg='grey',fg='black',
               font=('Helvetica',20,'bold'),
               bd=4,command=added_value.log
               ).grid(row=3,column=4,pady=1)

btnExt = Button(calc,text='exp',width=6,height=2,
                bg='grey',fg='black',
                font=('Helvetica',20,'bold'),
                bd=4,command=added_value.exp
                ).grid(row=3,column=5,pady=1)

btnMod= Button(calc,text='Mod',width=6,height=2,
               bg='grey',fg='black',
               font=('Helvetica',20,'bold'),
               bd=4,command=lambda:added_value.operation('mod')
               ).grid(row=3,column=6,pady=1)

btnE   = Button(calc, text="e",width=6, 
                height=2,bg='grey',fg='black',
                font=('Helvetica',20,'bold'),
                bd=4,command=added_value.e
               ).grid(row=3, column= 7, pady = 1)
 

#Row 4 :

btnlog10= Button(calc,text='log10',width=6,height=2,
               bg='grey',fg='black',
               font=('Helvetica',20,'bold'),
               bd=4,command=added_value.log10
               ).grid(row=4,column=4,pady=1)

btnlog1p= Button(calc,text='log1p',width=6,height=2,
               bg='grey',fg='black',
               font=('Helvetica',20,'bold'),
               bd=4,command=added_value.log1p
               ).grid(row=4,column=5,pady=1)

btnexpm1= Button(calc,text='expm1',width=6,height=2,
               bg='grey',fg='black',
               font=('Helvetica',20,'bold'),
               bd=4,command=added_value.expm1
               ).grid(row=4,column=6,pady=1)

btngamma= Button(calc,text='gamma',width=6,height=2,
               bg='grey',fg='black',
               font=('Helvetica',20,'bold'),
               bd=4,command=added_value.lgamma
               ).grid(row=4,column=7,pady=1)


#row 5:

btnlog2=Button(calc,text='log2',width=6,height=2,
               bg='grey',fg='black',
               font=('Helvetica',20,'bold'),
               bd=4,command=added_value.log2
               ).grid(row=5,column=4,pady=1)

btndeg=Button(calc,text='deg',width=6,height=2,
               bg='grey',fg='black',
               font=('Helvetica',20,'bold'),
               bd=4,command=added_value.degrees
               ).grid(row=5,column=5,pady=1)

btnEconomyosh=Button(calc,text='Economyosh',width=6,height=2,
               bg='grey',fg='black',
               font=('Helvetica',20,'bold'),
               bd=4,command=added_value.Economyosh
               ).grid(row=5,column=6,pady=1)

btnasinh=Button(calc,text='asinh',width=6,height=2,
               bg='grey',fg='black',
               font=('Helvetica',20,'bold'),
               bd=4,command=added_value.asinh
               ).grid(row=5,column=7,pady=1)

lblDisplay=Label(calc,text='Scientific Calculator',
               font=('Helvetica',30,'bold'),
               bg="grey",fg='black',justify=CENTER)
lblDisplay.grid(row=0,column=4,columnspan=4)

def iExit():
    def iExit(): 
        iExit = tkinter.messagebox.askyesno("Scientific Calculator",
                                        "Do you want to exit ?")
        if iExit>0:
            root.destroy()
            return

def Scientific():
    root.resizable(width=False,height=False)
    root.geometry("944x568+0+0")

def Genaral():
    root.resizable(width=False,height=False)
    root.geometry('480x568+0+0')
menubar = Menu(calc)

#ManuBar 1:

filemenu = Menu(menubar,tearoff = 0)
menubar.add_cascade(label='file',menu = filemenu)
filemenu.add_command(label='Genaral',command=Genaral)
filemenu.add_command(label='Scientific',command=Scientific)
filemenu.add_separator()
filemenu.add_command(label='Exit',command=iExit)
#ManuBar 2 :
editmenu = Menu(menubar,tearoff = 0)
menubar.add_cascade(label='Edit',menu = editmenu)
editmenu.add_command(label='Cut')
editmenu.add_command(label='Copy')
editmenu.add_separator()
editmenu.add_command(label ='Past')
root.config(menu=menubar)
root.mainloop()
