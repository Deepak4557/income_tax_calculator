# income_tax_calculator
#Collage assignment
import tkinter
from tkinter import *
from tkinter import ttk
import time

root = tkinter.Tk()  # defining main window
root.title("INCOME TAX CALCULATOR")
root.geometry('1028x400')
root.config(bg="#091833")
root.resizable(0, 0)
# fonts
font11 = "{U.S.101} 20 bold"
font2 = "{Segoe UI} 13 bold"
font3 = "Arial 13 bold"
font4 = "{Courier New} 10 bold"
font5 = "{Courier New} 10 normal"
localtime = time.asctime(time.localtime(time.time()))
# defining labels
a1 = tkinter.Label(root, text="INCOME TAX CALCULATOR", bg="#091833", fg="orange", font=font11)
a1.place(relx=0.268, rely=0.02, height=51, width=507)
a2 = tkinter.Label(root, text="Select the type of service", bg="#091833", fg="white", font=font2)
a2.place(x=410, y=90)
a = tkinter.Label(root, text=localtime, bg="#091833", fg="steel blue", font=font2)
a.place(x=410, y=50)


# define the fuction
def Govt_emp():
    # defining another window
    newwindow = tkinter.Toplevel(root)
    newwindow.title("Govt emp Income Tax")
    newwindow.geometry('500x400+600+40')
    newwindow.config(bg="#091833")


    a3 = tkinter.Label(newwindow, text="Income Tax Details", bg="#091833", fg="white",font=("Aries", 15, "bold"))
    a3.place(x=200, y=25)
    a10 = tkinter.Label(newwindow, text="#2.5L-5L:5%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=40)
    a10 = tkinter.Label(newwindow, text="#5L-7.5L:10%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=70)
    a10 = tkinter.Label(newwindow, text="#7.5L-10L:15%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=100)
    a10 = tkinter.Label(newwindow, text="#10L-12.5L:20%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=130)
    a10 = tkinter.Label(newwindow, text="#12.5L-15L:25%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=160)
    a10 = tkinter.Label(newwindow, text="#Above 15L:30%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=190)
    a4 = tkinter.Label(newwindow, text="Name of the Person", bg="#091833", fg="white", font=
    font2)
    a4.place(x=150, y=60)
    name1_entry = StringVar()
    name1_entry = tkinter.Entry(newwindow, textvariable=name1_entry, width=25)
    name1_entry.place(x=400, y=65)
    a5 = tkinter.Label(newwindow, text="Type of occupation", bg="#091833", fg="white",
                       font=font3)
    a5.place(x=150, y=95)
    name_entry = StringVar()
    name_entry = tkinter.Entry(newwindow, textvariable=name_entry, width=25)
    name_entry.place(x=400, y=100)
    a6 = tkinter.Label(newwindow, text="Annual Income Salary", bg="#091833", fg="white",
                       font=font3)
    a6.place(x=150, y=130)
    tax_entry1 = IntVar()
    tax_entry1 = tkinter.Entry(newwindow, textvariable=tax_entry1, width=25)
    tax_entry1.place(x=400, y=135)
    a7 = tkinter.Label(newwindow, text="Percentage of Tax ", bg="#091833", fg="white", font
    =font3)
    a7.place(x=150, y=165)
    tax_entry2 = IntVar()
    tax_entry2 = tkinter.Entry(newwindow, textvariable=tax_entry2, width=25)
    tax_entry2.place(x=400, y=170)
    def print_bill():
        num = float(tax_entry1.get())
        num0 = float(tax_entry2.get())
        result = num*num0/100
        total=str(result)
        p = tkinter.Label(newwindow, text="Person name: " + name1_entry.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        p.place(x=250, y=230)
        p1 = tkinter.Label(newwindow, text="Person occupation: " + name_entry.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        p1.place(x=250, y=255)
        p2 = tkinter.Label(newwindow, text="Annual Income: " + tax_entry1.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        p2.place(x=250, y=280)
        p3 = tkinter.Label(newwindow, text="Percentage of Tax: " + tax_entry2.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        p3.place(x=250, y=310)
        p4 = tkinter.Label(newwindow, text="Total Annual Tax: " + total, bg="#091833", fg=
        "white", font=font3, width=30)
        p4.place(x=250, y=340)
        def save_info():
            emp_name = name1_entry.get()
            Occup_name = name_entry.get()
            entry_sal = tax_entry1.get()
            entry_per = tax_entry2.get()
            total_tax = total
            print("person name :", emp_name)
            print("Occupation name :", Occup_name)
            print("Annual Income :", entry_sal)
            print("tax percentage :", entry_per)
            file = open("four.txt", "a")
            file.write("Person name: " + emp_name)
            file.write("\n")
            file.write("occupation name: " + Occup_name)
            file.write("\n")
            file.write("Annual salary: " + str(entry_sal))
            file.write("\n")
            file.write("tax percentage: " + str(entry_per))
            file.write("\n")
            file.write("Total Income Tax: " + total_tax)
            file.write("\n")
            file.close()
        return save_info()

    bill_btn1 = tkinter.Button(newwindow, text="Print bill", command=print_bill)
    bill_btn1.place(x=400, y=200)


def Private_emp():
    # defining another window
    newwindow = tkinter.Toplevel(root)
    newwindow.title("Private emp Income Tax")
    newwindow.geometry('500x400+600+40')
    newwindow.config(bg="#091833")

    b = tkinter.Label(newwindow, text="Income Tax Details", bg="#091833", fg="white",font=("Aries", 15, "bold"))
    b.place(x=200, y=25)
    a10 = tkinter.Label(newwindow, text="#2.5L-5L:5%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=40)
    a10 = tkinter.Label(newwindow, text="#5L-7.5L:10%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=70)
    a10 = tkinter.Label(newwindow, text="#7.5L-10L:15%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=100)
    a10 = tkinter.Label(newwindow, text="#10L-12.5L:20%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=130)
    a10 = tkinter.Label(newwindow, text="#12.5L-15L:25%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=160)
    a10 = tkinter.Label(newwindow, text="#Above 15L:30%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=190)
    b1 = tkinter.Label(newwindow, text="Name of the person", bg="#091833", fg="white", font=
    font2)
    b1.place(x=150, y=60)
    name1_entry = StringVar()
    name1_entry = tkinter.Entry(newwindow, textvariable=name1_entry, width=25)
    name1_entry.place(x=400, y=65)
    b2 = tkinter.Label(newwindow, text="Type of occupation", bg="#091833", fg="white",
                       font=font3)
    b2.place(x=150, y=95)
    name_entry = StringVar()
    name_entry = tkinter.Entry(newwindow, textvariable=name_entry, width=25)
    name_entry.place(x=400, y=100)
    b3 = tkinter.Label(newwindow, text="Annual Income Salary", bg="#091833", fg="white",
                       font=font3)
    b3.place(x=150, y=130)
    tax_entry1 = IntVar()
    tax_entry1 = tkinter.Entry(newwindow, textvariable=tax_entry1, width=25)
    tax_entry1.place(x=400, y=135)
    b4 = tkinter.Label(newwindow, text="Percentage of Tax ", bg="#091833", fg="white", font
    =font3)
    b4.place(x=150, y=165)
    tax_entry2 = IntVar()
    tax_entry2 = tkinter.Entry(newwindow, textvariable=tax_entry2, width=25)
    tax_entry2.place(x=400, y=170)
    def print_bill():
        num = float(tax_entry1.get())
        num0 = float(tax_entry2.get())
        result = num*num0/100
        total = str(result)
        q = tkinter.Label(newwindow, text="person name: " + name1_entry.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        q.place(x=250, y=230)
        q1 = tkinter.Label(newwindow, text="person occupation: " + name_entry.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        q1.place(x=250, y=255)
        q2 = tkinter.Label(newwindow, text="Annual Income: " + tax_entry1.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        q2.place(x=250, y=280)
        q3 = tkinter.Label(newwindow, text="Percentage of Tax: " + tax_entry2.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        q3.place(x=250, y=310)
        q4 = tkinter.Label(newwindow, text="Total Tax: " + total, bg="#091833", fg=
        "white", font=font3, width=30)
        q4.place(x=250, y=340)

        def save_info():
            emp_name = name1_entry.get()
            Occup_name = name_entry.get()
            entry_sal = tax_entry1.get()
            entry_per = tax_entry2.get()
            total_tax = total
            print("Person name :", emp_name)
            print("Occupation name :", Occup_name)
            print("Annual Income :", entry_sal)
            print("tax percentage :", entry_per)
            file = open("four.txt", "a")
            file.write("person name: " + emp_name)
            file.write("\n")
            file.write("occupation name: " + Occup_name)
            file.write("\n")
            file.write("Annual salary: " + str(entry_sal))
            file.write("\n")
            file.write("tax percentage: " + str(entry_per))
            file.write("\n")
            file.write("Total Income: " + total_tax)
            file.write("\n")
            file.close()
        return save_info()

    bill_btn1 = tkinter.Button(newwindow, text="Print bill", command=print_bill)
    bill_btn1.place(x=400, y=200)


def outsourceing_emp():
    # defining another window
    newwindow = tkinter.Toplevel(root)
    newwindow.title("Outsourceing emp Income Tax")
    newwindow.geometry('500x400+600+40')
    newwindow.config(bg="#091833")

    c0 = tkinter.Label(newwindow, text="Income Tax Details", bg="#091833", fg="white",font=("Aries", 15, "bold"))
    c0.place(x=200, y=25)
    a10 = tkinter.Label(newwindow, text="#2.5L-5L:5%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=40)
    a10 = tkinter.Label(newwindow, text="#5L-7.5L:10%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=70)
    a10 = tkinter.Label(newwindow, text="#7.5L-10L:15%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=100)
    a10 = tkinter.Label(newwindow, text="#10L-12.5L:20%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=130)
    a10 = tkinter.Label(newwindow, text="#12.5L-15L:25%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=160)
    a10 = tkinter.Label(newwindow, text="#Above 15L:30%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=190)
    c1 = tkinter.Label(newwindow, text="Name of the Person", bg="#091833", fg="white", font=
    font2)
    c1.place(x=150, y=60)
    name1_entry = StringVar()
    name1_entry = tkinter.Entry(newwindow, textvariable=name1_entry, width=25)
    name1_entry.place(x=400, y=65)
    c2 = tkinter.Label(newwindow, text="Type of occupation", bg="#091833", fg="white",
                       font=font3)
    c2.place(x=150, y=95)
    name_entry = StringVar()
    name_entry = tkinter.Entry(newwindow, textvariable=name_entry, width=25)
    name_entry.place(x=400, y=100)
    c3 = tkinter.Label(newwindow, text="Annual Income Salary", bg="#091833", fg="white",
                       font=font3)
    c3.place(x=150, y=130)
    tax_entry1 = IntVar()
    tax_entry1 = tkinter.Entry(newwindow, textvariable=tax_entry1, width=25)
    tax_entry1.place(x=400, y=135)
    c4 = tkinter.Label(newwindow, text="Percentage of Tax ", bg="#091833", fg="white", font
    =font3)
    c4.place(x=150, y=165)
    tax_entry2 = IntVar()
    tax_entry2 = tkinter.Entry(newwindow, textvariable=tax_entry2, width=25)
    tax_entry2.place(x=400, y=170)
    def print_bill():
        num = float(tax_entry1.get())
        num0 = float(tax_entry2.get())
        result = num*num0/100
        total = str(result)

        r = tkinter.Label(newwindow, text="Person name: " + name1_entry.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        r.place(x=250, y=230)
        r1 = tkinter.Label(newwindow, text="Person occupation: " + name_entry.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        r1.place(x=250, y=255)
        r2 = tkinter.Label(newwindow, text="Annual Income: " + tax_entry1.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        r2.place(x=250, y=280)
        r3 = tkinter.Label(newwindow, text="Percentage of Tax: " + tax_entry2.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        r3.place(x=250, y=310)
        r4 = tkinter.Label(newwindow, text="Total Tax: " + total, bg="#091833", fg=
        "white", font=font3, width=30)
        r4.place(x=250, y=340)
        def save_info():
            emp_name = name1_entry.get()
            Occup_name = name_entry.get()
            entry_sal = tax_entry1.get()
            entry_per = tax_entry2.get()
            total_tax = total
            print("Person name :", emp_name)
            print("Occupation name :", Occup_name)
            print("Annual Income :", entry_sal)
            print("tax percentage :", entry_per)
            file = open("four.txt", "a")
            file.write("Person name: " + emp_name)
            file.write("\n")
            file.write("occupation name: " + Occup_name)
            file.write("\n")
            file.write("Annual salary: " + str(entry_sal))
            file.write("\n")
            file.write("tax percentage: " + str(entry_per))
            file.write("\n")
            file.write("Total Income tax: " + total_tax)
            file.write("\n")
            file.close()
        return save_info()

    bill_btn1 = tkinter.Button(newwindow, text="Print bill", command=print_bill)
    bill_btn1.place(x=400, y=200)

def others():
    # defining another window
    newwindow = tkinter.Toplevel(root)
    newwindow.title("Others emp Income Tax")
    newwindow.geometry('500x400+600+40')
    newwindow.config(bg="#091833")

    d0 = tkinter.Label(newwindow, text="Income Tax Details", bg="#091833", fg="white",font=("Aries", 15, "bold"))
    d0.place(x=200, y=25)
    a10 = tkinter.Label(newwindow, text="#2.5L-5L:5%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=40)
    a10 = tkinter.Label(newwindow, text="#5L-7.5L:10%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=70)
    a10 = tkinter.Label(newwindow, text="#7.5L-10L:15%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=100)
    a10 = tkinter.Label(newwindow, text="#10L-12.5L:20%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=130)
    a10 = tkinter.Label(newwindow, text="#12.5L-15L:25%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=160)
    a10 = tkinter.Label(newwindow, text="#Above 15L:30%", bg="#091833", fg="white", font=("Aries", 15, "bold"))
    a10.place(x=800, y=190)
    d1 = tkinter.Label(newwindow, text="Name of the Person", bg="#091833", fg="white", font=
    font2)
    d1.place(x=150, y=60)
    name1_entry = StringVar()
    name1_entry = tkinter.Entry(newwindow, textvariable=name1_entry, width=25)
    name1_entry.place(x=400, y=65)
    d2 = tkinter.Label(newwindow, text="Type of occupation", bg="#091833", fg="white",
                       font=font3)
    d2.place(x=150, y=95)
    name_entry = StringVar()
    name_entry = tkinter.Entry(newwindow, textvariable=name_entry, width=25)
    name_entry.place(x=400, y=100)
    d3 = tkinter.Label(newwindow, text="Annual Income Salary", bg="#091833", fg="white",
                       font=font3)
    d3.place(x=150, y=130)
    tax_entry1 = IntVar()
    tax_entry1 = tkinter.Entry(newwindow, textvariable=tax_entry1, width=25)
    tax_entry1.place(x=400, y=135)
    d4 = tkinter.Label(newwindow, text="Percentage of Tax ", bg="#091833", fg="white", font
    =font3)
    d4.place(x=150, y=165)
    tax_entry2 = IntVar()
    tax_entry2 = tkinter.Entry(newwindow, textvariable=tax_entry2, width=25)
    tax_entry2.place(x=400, y=170)
    def print_bill():
        num = float(tax_entry1.get())
        num0 = float(tax_entry2.get())
        result = num*num0/100
        total = str(result)

        s = tkinter.Label(newwindow, text="person name: " + name1_entry.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        s.place(x=250, y=230)
        s1 = tkinter.Label(newwindow, text="person occupation: " + name_entry.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        s1.place(x=250, y=255)
        s2 = tkinter.Label(newwindow, text="Annual Income: " + tax_entry1.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        s2.place(x=250, y=280)
        s3 = tkinter.Label(newwindow, text="Percentage of Tax: " + tax_entry2.get(), bg="#091833", fg=
        "white", font=font3, width=30)
        s3.place(x=250, y=310)
        s4 = tkinter.Label(newwindow, text="Total Tax: " + total, bg="#091833", fg=
        "white", font=font3, width=30)
        s4.place(x=250, y=340)
        def save_info():
            emp_name = name1_entry.get()
            Occup_name = name_entry.get()
            entry_sal = tax_entry1.get()
            entry_per = tax_entry2.get()
            total_tax = total
            print("Person name :", emp_name)
            print("Occupation name :", Occup_name)
            print("Annual Income :", entry_sal)
            print("tax percentage :", entry_per)
            file = open("four.txt", "a")
            file.write("Person name: " + emp_name)
            file.write("\n")
            file.write("occupation name: " + Occup_name)
            file.write("\n")
            file.write("Annual salary: " + str(entry_sal))
            file.write("\n")
            file.write("tax percentage: " + str(entry_per))
            file.write("\n")
            file.write("Total Income Tax: " + total_tax)
            file.write("\n")
            file.close()
        return save_info()

    bill_btn1 = tkinter.Button(newwindow, text="Print bill", command=print_bill)
    bill_btn1.place(x=400, y=200)
#defining buttons
btn1 = tkinter.Button(root, text= "Private_emp",borderwidth = 5,width = 10, command = Private_emp)
btn1.place(x = 470, y = 150)
btn2 =tkinter.Button(root,text = "outsourceing_emp",borderwidth = 5,width = 15, command = outsourceing_emp)
btn2.place(x = 470, y = 200)
btn3 =tkinter.Button(root,text = "Govt_emp",borderwidth = 5,width = 10,command = Govt_emp)
btn3.place(x = 470, y = 250)
btn4 =tkinter.Button(root,text = "Others",borderwidth = 5,width = 10,command = others)
btn4.place(x = 470, y = 300)
root.mainloop()
