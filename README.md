# Restaurant-Management-System
Python project

from tkinter import*
import random
import time
import datetime

root=Tk()
root.geometry("1600x8000")
root.title("Restaurant Management System")

Tops=Frame(root, width=1600,relief=RAISED)
Tops.pack(side=TOP)

f1=Frame(root,width=1000,height=700,relief=RAISED)
f1.pack(side=LEFT)



#=================================================================================
#                  TIME
#================================================================================
localtime=time.asctime(time.localtime(time.time()))

lblInfo=Label(Tops,font=('helvetica',50,'bold'),text="IT'S MY RESTAURANT ",fg="RED",bd=10,anchor='center')
lblInfo.grid(row=0,column=0)

lblInfo=Label(Tops,font=('arial',20,'bold'),text=localtime,fg="Blue",bd=10,anchor='center')
lblInfo.grid(row=1,column=0)

def Ref():
    x=random.randint(10001,20000)
    randomRef=str(x)
    rand.set(randomRef)

    if (Fries.get()==""):
        CoFries=0
    else:
        CoFries=float(Fries.get())


    
    if (Noodles.get()==""):
        CoNoodles=0
    else:
        CoNoodles=float(Noodles.get())



    if (Soup.get()==""):
        CoSoup=0
    else:
        CoSoup=float(Soup.get())



    if (Burger.get()==""):
        CoBurger=0
    else:
        CoBurger=float(Burger.get())

        
    if (Sandwich.get()==""):
        CoSandwich=0
    else:
        CoSandwich=float(Sandwich.get())

     
    if (Drinks.get()==""):
        CoD=0
    else:
        CoD=float(Drinks.get())

                   
    CostofFries =CoFries * 30
    CostofDrinks=CoD * 40
    CostofNoodles = CoNoodles* 60
    CostofSoup = CoSoup * 65
    CostBurger = CoBurger* 50
    CostSandwich=CoSandwich * 40

    CostofMeal= "Rs", str('%.2f' % (CostofFries+CostofDrinks+CostofNoodles+CostofSoup+CostBurger+CostSandwich))

    PayTax=((CostofFries+CostofDrinks+CostofNoodles+CostofSoup+CostBurger+CostSandwich) * 2.5/100)

    TotalCost=(CostofFries+CostofDrinks+CostofNoodles+CostofSoup+CostBurger+CostSandwich)
 
    Ser_Charge= ((CostofFries+CostofDrinks+CostofNoodles+CostofSoup+CostBurger+CostSandwich)/99)

    Service = "Rs", str ('%.2f' % Ser_Charge)

    OverAllCost ="Rs", str ('%.2f' % (2*PayTax+TotalCost+Ser_Charge))

    PaidTax= "Rs", str ('%.2f' % PayTax)

    Service_Charge.set(Service)
    Cost.set(CostofMeal)
    Tax.set(PaidTax)
    SubTotal.set(CostofMeal)
    Total.set(OverAllCost)
    
def qExit():
    root.destroy()

def Reset():
    rand.set("") 
    Fries.set("")
    Noodles.set("")
    Soup.set("")
    SubTotal.set("")
    Total.set("")
    Service_Charge.set("")
    Drinks.set("")
    Tax.set("")
    Cost.set("")
    Burger.set("")
    Sandwich.set("")

def price():
    roo = Tk()
    roo.geometry("600x220+0+0")
    roo.title("Price List")
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="ITEM", fg="black", bd=2)
    lblinfo.grid(row=0, column=0)
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="PRICE", fg="black", anchor=W)
    lblinfo.grid(row=0, column=1)
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="Fries", fg="steel blue", anchor=W)
    lblinfo.grid(row=1, column=0)
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="30", fg="steel blue", anchor=W)
    lblinfo.grid(row=1, column=1)
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="Noodles", fg="steel blue", anchor=W)
    lblinfo.grid(row=2, column=0)
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="60", fg="steel blue", anchor=W)
    lblinfo.grid(row=2, column=1)
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="Soup", fg="steel blue", anchor=W)
    lblinfo.grid(row=3, column=0)
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="65", fg="steel blue", anchor=W)
    lblinfo.grid(row=3, column=1)
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="Burger", fg="steel blue", anchor=W)
    lblinfo.grid(row=4, column=0)
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="50", fg="steel blue", anchor=W)
    lblinfo.grid(row=4, column=1)
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="Sandwich", fg="steel blue", anchor=W)
    lblinfo.grid(row=5, column=0)
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="40", fg="steel blue", anchor=W)
    lblinfo.grid(row=5, column=1)
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="Drinks", fg="steel blue", anchor=W)
    lblinfo.grid(row=6, column=0)
    lblinfo = Label(roo, font=('arial', 15, 'bold'), text="40", fg="steel blue", anchor=W)
    lblinfo.grid(row=6, column=1)

    roo.mainloop()
#====================================Restaraunt Info 1===========================================================

rand = StringVar()
Fries=StringVar()
Noodles=StringVar()
Soup=StringVar()
SubTotal=StringVar()
Total=StringVar()
Service_Charge=StringVar()
Drinks=StringVar()
Tax=StringVar()
Cost=StringVar()
Burger=StringVar()
Sandwich=StringVar()


lblReference= Label(f1, font=('arial', 16, 'bold'),text="Reference",bd=16,anchor="w",fg='RED')
lblReference.grid(row=0, column=0)
txtReference=Entry(f1, font=('arial',16,'bold'),textvariable=rand,bd=10,insertwidth=4,bg="lime",justify='right')
txtReference.grid(row=0,column=1)


lblFries= Label(f1, font=('arial', 16, 'bold'),text="Fries",bd=16,anchor="w",fg='RED')
lblFries.grid(row=1, column=0)
txtFries=Entry(f1, font=('arial',16,'bold'),textvariable=Fries,bd=10,insertwidth=4,bg="lime",justify='right')
txtFries.grid(row=1,column=1)


lblNoodles= Label(f1, font=('arial', 16, 'bold'),text="Noodles",bd=16,anchor="w",fg='RED')
lblNoodles.grid(row=2, column=0)
txtNoodles=Entry(f1, font=('arial',16,'bold'),textvariable=Noodles,bd=10,insertwidth=4,bg="lime",justify='right')
txtNoodles.grid(row=2,column=1)


lblSoup= Label(f1, font=('arial', 16, 'bold'),text="Soup",bd=16,anchor="w",fg='RED')
lblSoup.grid(row=3, column=0)
txtSoup=Entry(f1, font=('arial',16,'bold'),textvariable=Soup,bd=10,insertwidth=4,bg="lime",justify='right')
txtSoup.grid(row=3,column=1)

lblBurger= Label(f1, font=('arial', 16, 'bold'),text="Burger",bd=16,anchor="w",fg='RED')
lblBurger.grid(row=4, column=0)
txtBurger=Entry(f1, font=('arial',16,'bold'),textvariable=Burger,bd=10,insertwidth=4,bg="lime",justify='right')
txtBurger.grid(row=4,column=1)

lblSandwich= Label(f1, font=('arial', 16, 'bold'),text="Sandwich",bd=16,anchor="w",fg='RED')
lblSandwich.grid(row=5, column=0)
txtSandwich=Entry(f1, font=('arial',16,'bold'),textvariable=Sandwich,bd=10,insertwidth=4,bg="lime",justify='right')
txtSandwich.grid(row=5,column=1)

#============================================================================================================
#                                RESTAURANT INFO 2
#============================================================================================================

lblDrinks= Label(f1, font=('arial', 16, 'bold'),text="Drinks",bd=16,anchor="w",fg='RED')
lblDrinks.grid(row=0, column=2)
txtDrinks=Entry(f1, font=('arial',16,'bold'),textvariable=Drinks,bd=10,insertwidth=4,bg="lime",justify='right')
txtDrinks.grid(row=0,column=3)

lblCost= Label(f1, font=('arial', 16, 'bold'),text="Cost of Meal",bd=16,anchor="w",fg='RED')
lblCost.grid(row=1, column=2)
txtCost=Entry(f1, font=('arial',16,'bold'),textvariable=Cost,bd=10,insertwidth=4,bg="lime",justify='right')
txtCost.grid(row=1,column=3)


lblService= Label(f1, font=('arial', 16, 'bold'),text="Restaurnt Charges",bd=16,anchor="w",fg='RED')
lblService.grid(row=2, column=2)
txtService=Entry(f1, font=('arial',16,'bold'),textvariable=Service_Charge,bd=10,insertwidth=4,bg="lime",justify='right')
txtService.grid(row=2,column=3)


lblStateTax= Label(f1, font=('arial', 16, 'bold'),text="CGST",bd=16,anchor="w",fg='RED')
lblStateTax.grid(row=3, column=2)
txtStateTax=Entry(f1, font=('arial',16,'bold'),textvariable=Tax,bd=10,insertwidth=4,bg="lime",justify='right')
txtStateTax.grid(row=3,column=3)

lblSubTotal= Label(f1, font=('arial', 16, 'bold'),text="SGST",bd=16,anchor="w",fg='RED')
lblSubTotal.grid(row=4, column=2)
txtSubTotal=Entry(f1, font=('arial',16,'bold'),textvariable=Tax,bd=10,insertwidth=4,bg="lime",justify='right')
txtSubTotal.grid(row=4,column=3)

lblTotalCost= Label(f1, font=('arial', 16, 'bold'),text="Total Cost",bd=16,anchor="w",fg='RED')
lblTotalCost.grid(row=5, column=2)
txtTotalCost=Entry(f1, font=('arial',16,'bold'),textvariable=Total,bd=10,insertwidth=4,bg="lime",justify='right')
txtTotalCost.grid(row=5,column=3)

#===================================================Buttons==========================================================================================
btnTotal=Button(f1,padx=16,pady=8,bd=16,fg="red",font=('arial',16,'bold'),width=10,text="Total",bg="cyan",command=Ref).grid(row=7,column=0)

btnReset=Button(f1,padx=16,pady=8,bd=16,fg="red",font=('arial',16,'bold'),width=10,text="Reset",bg="cyan",command=Reset).grid(row=7,column=1)

btnExit=Button(f1,padx=16,pady=8,bd=16,fg="red",font=('arial',16,'bold'),width=10,text="Exit",bg="cyan",command=qExit).grid(row=7,column=2)

btnprice=Button(f1,padx=16,pady=8, bd=10 ,fg="red",font=('ariel' ,16,'bold'),width=10, text="Price", bg="cyan",command=price).grid(row=7, column=3)



root.mainloop()


