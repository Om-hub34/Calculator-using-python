# Calculator using Python

from tkinter import *

root = Tk()

root.title("Calculator")  #right

root.geometry("450x450")
root.resizable(1, 1)
root.config(bg="black")

re = Label(root, text="", font=("Arial", 20), bg="black", fg="white")
re.grid(row=0, column=0, columnspan=4, pady=(10, 20))
re.configure(font=("Helvetica", 25, "bold"))

btn = Button(root, text="7", font=("Arial", 14), bg="gray", fg="white", width=5, height=2,command=lambda:get_digit(7))
btn.grid(row=1, column=0, padx=5, pady=5)
btn.configure(font=("Helvetica", 18, "bold"))

btn1 = Button(root, text="8", font=("Arial", 14), bg="gray", fg="white", width=5, height=2,command=lambda:get_digit(8))
btn1.grid(row=1, column=1, padx=5, pady=5)
btn1.configure(font=("Helvetica", 18, "bold"))

btn2 = Button(root, text="9", font=("Arial", 14), bg="gray", fg="white", width=5, height=2,command=lambda:get_digit(9))
btn2.grid(row=1, column=2, padx=5, pady=5)
btn2.configure(font=("Helvetica", 18, "bold"))

btn3 = Button(root, text="/", font=("Arial", 14), bg="orange", fg="white", width=5, height=2,command=lambda:operator_s("/"))
btn3.grid(row=1, column=3, padx=5, pady=5)
btn3.configure(font=("Helvetica", 18, "bold"))

btn4 = Button(root, text="4", font=("Arial", 14), bg="gray", fg="white", width=5, height=2,command=lambda:get_digit(4))
btn4.grid(row=2, column=0, padx=5, pady=5)
btn4.configure(font=("Helvetica", 18, "bold"))

btn5 = Button(root, text="5", font=("Arial", 14), bg="gray", fg="white", width=5, height=2,command=lambda:get_digit(5))
btn5.grid(row=2, column=1, padx=5, pady=5)
btn5.configure(font=("Helvetica", 18, "bold"))

btn6 = Button(root, text="6", font=("Arial", 14), bg="gray", fg="white", width=5, height=2,command=lambda:get_digit(6))
btn6.grid(row=2, column=2, padx=5, pady=5)  
btn6.configure(font=("Helvetica", 18, "bold"))

btn7 = Button(root, text="*", font=("Arial", 14), bg="orange", fg="white", width=5, height=2,command=lambda:operator_s("*"))
btn7.grid(row=2, column=3, padx=5, pady=5)
btn7.configure(font=("Helvetica", 18, "bold"))

btn8 = Button(root, text="1", font=("Arial", 14), bg="gray", fg="white", width=5, height=2,command=lambda:get_digit(1))
btn8.grid(row=3, column=0, padx=5, pady=5)
btn8.configure(font=("Helvetica", 18, "bold"))

btn9 = Button(root, text="2", font=("Arial", 14), bg="gray", fg="white", width=5, height=2,command=lambda:get_digit(2))
btn9.grid(row=3, column=1, padx=5, pady=5)
btn9.configure(font=("Helvetica", 18, "bold"))

btn10 = Button(root, text="3", font=("Arial", 14), bg="gray", fg="white", width=5, height=2,command=lambda:get_digit(3))
btn10.grid(row=3, column=2, padx=5, pady=5)
btn10.configure(font=("Helvetica", 18, "bold"))

btn11 = Button(root, text="-", font=("Arial", 14), bg="orange", fg="white", width=5, height=2,command=lambda:operator_s("-"))
btn11.grid(row=3, column=3, padx=5, pady=5)
btn11.configure(font=("Helvetica", 18, "bold"))

btn12 = Button(root, text="0", font=("Arial", 14), bg="gray", fg="white", width=5, height=2,command=lambda:get_digit(0))
btn12.grid(row=4, column=0, padx=5, pady=5)
btn12.configure(font=("Helvetica", 18, "bold"))

btn13 = Button(root, text="C", font=("Arial", 14), bg="red", fg="white", width=5, height=2,command=lambda:clear_display())
btn13.grid(row=4, column=1, padx=5, pady=5)
btn13.configure(font=("Helvetica", 18, "bold"))

btn14 = Button(root, text="=", font=("Arial", 14), bg="green", fg="white", width=5, height=2,command=lambda:result())
btn14.grid(row=4, column=2, padx=5, pady=5)
btn14.configure(font=("Helvetica", 18, "bold"))

btn15 = Button(root, text="+", font=("Arial", 14), bg="orange", fg="white", width=5, height=2,command=lambda:operator_s("+"))
btn15.grid(row=4, column=3, padx=5, pady=5)
btn15.configure(font=("Helvetica", 18, "bold"))

def clear_display():
    re.config(text="")

def get_digit(digit):     #right
    current = re['text']
    new = current + str(digit)
    re.config(text=new) 

def operator_s(op):
    global first_num, oper
    first_num=float(re['text'])
    oper = op
    re.config(text="")

def result():
    global first_num, oper
    s_num= float(re['text'])
    if oper == "+":
        res= first_num + s_num
        re.config(text=str(res))
    elif oper == "-":
        res= first_num - s_num
        re.config(text=str(res))
    elif oper == "*":
        res= first_num * s_num
        re.config(text=str(res))
    elif oper == "/":
        if s_num == 0:
            re.config(text="Error")
        else:
            res= first_num / s_num
            re.config(text=str(res))


root.mainloop()
