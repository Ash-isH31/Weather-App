from tkinter import *
from tkinter import ttk
import requests

def data_get():
    city = city_name.get()
    api_key = "8258287bcca725623e7ca3aa4d6cea38"
    url = f"https://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}"
    
    data = requests.get(url).json()
    
    try:
        w_label1.config(text=data["weather"][0]["main"])
        w_label2.config(text=data["weather"][0]["description"])
        temp = data["main"]["temp"]
        w_label3.config(text=str(int(temp - 273.15)) + " °C")
        w_label4.config(text=str(data["main"]["pressure"]) + " hPa")
    except KeyError:
        w_label1.config(text="N/A")
        w_label2.config(text="Invalid City")
        w_label3.config(text="N/A")
        w_label4.config(text="N/A")

win = Tk()
win.title("WEATHER APP")
win.config(bg="black")
win.geometry("600x600")

name_label = Label(win, text="WEATHER APP", font=("Times New Roman", 30, "bold"))
name_label.place(x=60, y=70, height=60, width=500)

city_name = StringVar()
list_name = ["Andhra Pradesh", "Arunachal Pradesh", "Assam", "Bihar", "Chhattisgarh", "Goa", "Gujarat", 
             "Haryana", "Himachal Pradesh", "Jammu and Kashmir", "Jharkhand", "Karnataka", "Kerala", 
             "Madhya Pradesh", "Maharashtra", "Manipur", "Meghalaya", "Mizoram", "Nagaland", "Odisha", 
             "Punjab", "Rajasthan", "Sikkim", "Tamil Nadu", "Telangana", "Tripura", "Uttar Pradesh", 
             "Uttarakhand", "West Bengal", "Andaman and Nicobar Islands", "Chandigarh", 
             "Dadra and Nagar Haveli", "Daman and Diu", "Lakshadweep", 
             "National Capital Territory of Delhi", "Puducherry"]

com = ttk.Combobox(win, values=list_name, font=("Times New Roman", 20), textvariable=city_name)
com.place(x=60, y=150, height=40, width=500)

done_button = Button(win, text=" DONE", font=("Times New Roman", 20, "bold"), command=data_get)
done_button.place(x=250, y=210, height=50, width=100)


Label(win, text="Weather Climate", font=("Times New Roman", 20)).place(x=30, y=300, height=45, width=400)
w_label1 = Label(win, font=("Times New Roman", 20))
w_label1.place(x=440, y=300, height=45, width=140)

Label(win, text="Weather Description", font=("Times New Roman", 20)).place(x=30, y=350, height=45, width=400)
w_label2 = Label(win, font=("Times New Roman", 10))
w_label2.place(x=440, y=350, height=45, width=140)

Label(win, text="Temperature", font=("Times New Roman", 20)).place(x=30, y=400, height=45, width=400)
w_label3 = Label(win, font=("Times New Roman", 20))
w_label3.place(x=440, y=400, height=45, width=140)

Label(win, text="Pressure", font=("Times New Roman", 20)).place(x=30, y=450, height=45, width=400)
w_label4 = Label(win, font=("Times New Roman", 20))
w_label4.place(x=440, y=450, height=45, width=140)

win.mainloop()
