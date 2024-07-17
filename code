import tkinter as tk
import tkinter.font as font
import mysql.connector as mycon
import csv
mydatabase=mycon.connect(host="localhost", user="root", passwd="apjkhg123", database="project") #CONNECTING TO MYSQL
mycursor=mydatabase.cursor()
#CREATING MYSQL TABLE :
mycursor.execute("CREATE TABLE if not exists entry(Date date, Time time, FlatNo int(3), Name varchar(20), PhoneNo bigint(10), Work varchar(20), Temp float(4), Entry char(10)) ")
mydatabase.commit()
def adding(): #ADDING ENTERED DATA TO TABLE
def dataentered(): #RETRIEVING ENTERED DATA a=flat.get()
a=int(a)
b=name.get() c=phoneno.get() d=lst.get(lst.curselection()) e=temp.get()
f=""
if float(e)>97: #TO CHECK IF TEMPERATURE IS HIGH f="Rejected"
e=float(e) ewindow=tk.Tk()
error=tk.Label(ewindow, text="You Cannot enter the society because your \ntemperature is high!!\nTake care!", bg='red', width=60, height=4)
error.pack() else:
f="Allowed" e=float(e)
if len(c)==10: #CHECKING IF ENTERED PHONE NO. IS 10 DIGITS c=int(c)
print("Successfully Added") window2.destroy()
myquery2="insert into entry values(NOW(), NOW(), '{}','{}','{}','{}','{}', '{}')".format(a,b,c,d,e,f) #INSERTING INFO IN MYSQL TABLE
mycursor.execute(myquery2)
mydatabase.commit() else:
c="Enter correct phone number"
ewindow=tk.Tk()
error=tk.Label(ewindow, text="Please Enter correct Phone number!", bg='red', width=60, height=2)
error.pack()
window2=tk.Tk() #DATAENTERINGWINDOW label=tk.Label(window2, text="Flat Number::", width=40, height=3)

flat=tk.Entry(window2,)
label1=tk.Label(window2, text="Name:", width=40, height=3) name=tk.Entry(window2,)
label2=tk.Label(window2, text="Phone Number:", width=40, height=3) phoneno=tk.Entry(window2,)
label.pack() flat.pack() label1.pack() name.pack() label2.pack() phoneno.pack()
label3=tk.Label(window2, text="Choose Work:", width=40, height=3) lst=tk.Listbox(window2, height=4, activestyle='none', width=40) lst.insert(1, "Friend")
lst.insert(1, "Relative")
lst.insert(1, "House Service") lst.insert(1, "Delivery")
label4=tk.Label(window2, text="Enter Temperature:", width=40, height=3) temp=tk.Entry(window2,)
enter=tk.Button(window2, text="Enter", command=dataentered, width=20, height=2)
label3.pack() lst.pack()

label4.pack() temp.pack() enter.pack() window2.mainloop()
def allentries(): #FOR DISPLAYING ALL THE ENTRIES myquery="select * from entry" mycursor.execute(myquery)
display=" "
for i in mycursor: print(i)
display= display + " | " + str(i[0]) + " | " + str(i[1]) + " | " + str(i[2]) + " | " + str(i[3]) + " | " + str(i[4]) + " | " + str(i[5]) + " | " + str(i[6]) + " | " + str(i[7]) +"\n"
outputwindow=tk.Tk()
output=tk.Frame(outputwindow, bg='blue', width=80, height=30) output1=tk.Label(output, text=display, width=60, height=30, fg='black')
output.pack() output1.pack()
def searchname(): #FOR DISPLAYING ENTRIES SEARCHED BY NAME. def entered(): #RETRIEVING THE NAME ENTERED TO BE SEARCHED
a=entername.get()
myquery="select * from entry where Name='{}'".format(a) mycursor.execute(myquery)
display=" "
for i in mycursor:
print(i)

display=display + " | " + str(i[0]) + " | " + str(i[1]) + " | " + str(i[2]) + " | " + str(i[3]) + " | " + str(i[4]) + " | " + str(i[5]) + " | " + str(i[6]) + " | " + str(i[7]) +"\n"
outputwindow=tk.Tk()
output=tk.Frame(outputwindow, bg='blue', width=80, height=30) output1=tk.Label(output, text=display, width=60, height=30, fg='black') output.pack()
output1.pack()
window4.destroy()
window4=tk.Tk()
label=tk.Label(window4, text="Enter name to be searched", width=40, height=5)
entername=tk.Entry(window4)
enter=tk.Button(window4, text="search", command=entered, width=15, height=2)
label.pack() entername.pack() enter.pack() window4.mainloop()
def searchphone(): #TO DISPLAY ENTRIES SEARCHED BY PHONE NO.
def entered(): #TO RETRIEVE PHONE NO. ENTERED TO BE SEARCHED
a=enterphone.get()
myquery="select * from entry where PhoneNo='{}'".format(a)
mycursor.execute(myquery) display=" "
for i in mycursor:
print(i)

display= display + " | " + str(i[0]) + " | " + str(i[1]) + " | " + str(i[2]) + " | " + str(i[3]) + " | " + str(i[4]) + " | " + str(i[5]) + " | " + str(i[6]) + " | " + str(i[7]) +"\n"
outputwindow=tk.Tk()
output=tk.Frame(outputwindow, bg='blue', width=80, height=30) output1=tk.Label(output, text=display, width=60, height=30, fg='black') output.pack()
output1.pack()
window4.destroy()
window4=tk.Tk()
label=tk.Label(window4, text="Enter phone number to be searched", width=40, height=5)
enterphone=tk.Entry(window4)
enter=tk.Button(window4, text="search", command=entered, width=15, height=2)
label.pack() enterphone.pack() enter.pack() window4.mainloop()
def searchflat(): #TO DISPLAY ENTRIES SEARCHED BY FLAT NO. def entered():
a=enterflat.get()
myquery="select * from entry where FlatNo='{}'".format(a) mycursor.execute(myquery)
display=" "
for i in mycursor:

print(i)
display= display + " | " + str(i[0]) + " | " + str(i[1]) + " | " + str(i[2]) + " | "+str(i[3])+"|"+str(i[4])+"|"+str(i[5])+"|"+str(i[6])+"|"+ str(i[7]) +"\n"
outputwindow=tk.Tk()
output=tk.Frame(outputwindow, bg='blue', width=80, height=30) output1=tk.Label(output, text=display, width=60, height=30, fg='black') output.pack()
output1.pack()
window4.destroy()
window4=tk.Tk()
label=tk.Label(window4, text="Enter Flat number to be searched", width=40, height=5)
enterflat=tk.Entry(window4)
enter=tk.Button(window4, text="Search", command=entered, width=15, height=2)
label.pack() enterflat.pack() enter.pack() window4.mainloop()
def searchdate(): #TO DISPLAY ENTRIES SEARCHED BY DATE def entered():
a=enterdate.get()
myquery="select * from entry where Date='{}'".format(a) mycursor.execute(myquery)

display=" "
for i in mycursor:
print(i)
display= display + " | " + str(i[0]) + " | " + str(i[1]) + " | " + str(i[2]) + " | " + str(i[3]) + " | " + str(i[4]) + " | " + str(i[5]) + " | " + str(i[6]) + " | " + str(i[7]) +"\n"
outputwindow=tk.Tk()
output=tk.Frame(outputwindow, bg='blue', width=80, height=30) output1=tk.Label(output, text=display, width=60, height=30, fg='black') output.pack()
output1.pack()
window4.destroy()
window4=tk.Tk()
label=tk.Label(window4, text="Enter Date(format=yyyy/mm/dd) to be searched", width=40, height=5)
enterdate=tk.Entry(window4)
enter=tk.Button(window4, text="Search", command=entered, width=15, height=2)
label.pack() enterdate.pack() enter.pack() window4.mainloop()
def searchwork(): #TO DISPLAY ENTRIES SEARCHED BY WORK def entered():
a=enterwork.get()
myquery="select * from entry where Work='{}'".format(a)

mycursor.execute(myquery) display=" "
for i in mycursor:
print(i)
display= display + " | " + str(i[0]) + " | " + str(i[1]) + " | " + str(i[2]) + " | " + str(i[3]) + " | " + str(i[4]) + " | " + str(i[5]) + " | " + str(i[6]) + " | " + str(i[7]) +"\n"
outputwindow=tk.Tk()
output=tk.Frame(outputwindow, bg='blue', width=80, height=30) output1=tk.Label(output, text=display, width=60, height=30, fg='black')
output.pack() output1.pack() window4.destroy()
window4=tk.Tk()
label=tk.Label(window4, text="Enter work to be searched", width=40, height=5) enterwork=tk.Entry(window4)
enter=tk.Button(window4, text="search", command=entered, width=15, height=2)
label.pack() enterwork.pack() enter.pack()
window4.mainloop()
def searchentry(): #FOR SEARCHING AN ENTRY window3=tk.Tk()
label=tk.Label(window3, text="Search by:", width=40, height=3)

name=tk.Button(window3, text="Name", command=searchname, width=30, height=3, pady=10, bg='lightsteelblue')
phone=tk.Button(window3, text="Phone number", command=searchphone, width=30, height=3, pady=10, bg='lightsteelblue')
date=tk.Button(window3, text="Date", command=searchdate, width=30, height=3, pady=10, bg='lightsteelblue')
work=tk.Button(window3, text="Work", command=searchwork, width=30, height=3, pady=10, bg='lightsteelblue')
flat=tk.Button(window3, text="Flat Number", command=searchflat, width=30, height=3, pady=10, bg='lightsteelblue')
label.pack() name.pack() phone.pack()
flat.pack() date.pack()
work.pack()
def close(): #FOR CLOSING SEARCH WINDOW window3.destroy()
close2=tk.Button(window3, text="Close", command=close, width=15, height=2) close2.pack()
def todayentry(): #TO DISPLAY TODAYS ENTRIES
myquery="select * from entry where Date=(select max(Date) from entry)" mycursor.execute(myquery)
display=" "
for i in mycursor:

print(i)
display= display + " | " + str(i[0]) + " | " + str(i[1]) + " | " + str(i[2]) + " | " + str(i[3]) + " | " + str(i[4]) + " | " + str(i[5]) + " | " + str(i[6]) + " | " + str(i[7]) +"\n"
outputwindow=tk.Tk()
output=tk.Frame(outputwindow, bg='blue', width=80, height=30) output1=tk.Label(output, text=display, width=60, height=30, fg='black') output.pack()
output1.pack()
def viewing(): #TO VIEW ENTRIES window2=tk.Tk()
label1=tk.Label(window2, text="Choose:", width=30, height=3)
viewall=tk.Button(window2, text="View All Entries",command=allentries, width=30, height=3, bg='lightsteelblue')
search=tk.Button(window2, text="Search For Entry", command=searchentry, width=30, height=3, bg='lightsteelblue')
latest=tk.Button(window2, text="View Today's Entry", command=todayentry, width=30, height=3, bg='lightsteelblue')
label1.pack() viewall.pack() search.pack() latest.pack()
def close(): window2.destroy()
close1=tk.Button(window2, text="Close", command=close, width=15, height=2)

close1.pack()
window2.mainloop()
def deleting(): #TO DELETE AN ENTRY window5=tk.Tk()
label1=tk.Label(window5, text="Enter name to be deleted:", width=30, height=3) name1=tk.Entry(window5)
def delentry(): a=name1.get()
myquery1="select * from entry where Name='{}'".format(a) myquery="delete from entry where Name='{}'".format(a)
mycursor.execute(myquery1) display=" Deleted Entry: \n " for i in mycursor:
print("Deleted entry: \n", i)
display= display + " | " + str(i[0]) + " | " + str(i[1]) + " | " + str(i[2]) + " | " + str(i[3]) + " | " + str(i[4]) + " | " + str(i[5]) + " | " + str(i[6]) + " | " + str(i[7]) +"\n"
outputwindow=tk.Tk()
output=tk.Frame(outputwindow, bg='blue', width=80, height=30) output1=tk.Label(output, text=display, width=60, height=30, fg='black') output.pack()
output1.pack()
mycursor.execute(myquery) window5.destroy()

delname=tk.Button(window5, text="Delete", command=delentry, width=20, height=2)
label1.pack() name1.pack() delname.pack()
#RESIDENT DETAILS
def resdetails():
def showdetails():
display="
x=str('project123')
enteredpass=password.get()
if str(enteredpass)==x: #CHECKING IF ENTERED PASSWORD IS CORRECT
with open('residents.csv', 'r') as file: data=csv.reader(file)
for i in data: forjini:
display=display + j + " | " display=display + "\n"
window7=tk.Tk()
output=tk.Frame(window7, width=80, height=50) output1=tk.Label(output, text=display, width=70, height=45) output.pack()
output1.pack()
window6.destroy()
RESIDENT DETAILS \n
----------------------------\n \n \n \n "

else:
#IF ENTERED PASSWORD IS WRONG output2=tk.Frame(window6, width=80, height=5)
output3=tk.Label(output2, text="Wrong Password!!", width=40, height=2, bg='red')
output2.pack() output3.pack()
window6=tk.Tk()
enterpass=tk.Label(window6, text="Enter password to view resident information", width=50, height=2)
password=tk.Entry(window6, show='*')
enter1=tk.Button(window6, text="Enter", command=showdetails, width=10, height=1, bg='grey85')
enterpass.pack() password.pack() enter1.pack()
def end1(): window.destroy()
#FILE HANDLING:
fields = ['Flat', 'Name', 'Phone Number', 'Number of residents']
rows = [ ['101', 'Akshaj Bisht', '8902030213', '4'], # Details of the resident ['102', 'Varad Dabir', '9904030546', '2'],
['201', 'Anshika Jhalani', '9834630980', '4'],
['202', 'Tushi Gogoi', '770403236', '3'],

['301', 'TK Srivaths', '7857230910', '4'],
['302', 'Abhinandan Mohanty', '9863540927', '3'], ['401', 'Suhani Manoria', '7865203973', '3'], ['402', 'Suhaani Chakote', '8930230303', '2'], ['501', 'Sana Deshmukh', '9603938920', '3'], ['502', 'Reetika Sharma', '7728208299', '4'], ['601', 'Bhoomi Nelwade', '9543029384', '3'], ['602', 'Aditi Singh', '9238478920', '4'],
['701', 'Aditya Pandey', '7865223890', '4'],
['702', 'Allen John', '9902883920', '3'] ]
# WRITING INTO CSV FILE
with open('residents.csv', 'w') as csvfile: csvwriter = csv.writer(csvfile) csvwriter.writerow(fields) csvwriter.writerows(rows)
csvfile.close()
#MAIN WINDOW:
window=tk.Tk()
frame1=tk.Frame(window, bg='blue', width=50, height=15)
myfont=font.Font(size = 16, family='Lucida Grande')
label=tk.Label(master=frame1, text="Welcome To Gokuldham Society", width=45, height=10, fg='black', bg='rosybrown1', font=myfont)
frame2=tk.Frame(window, bg='green', width=75, height=5)

add=tk.Button(master=frame2, text="Add Entry",width=55, height=4,fg="green",bg='lightslategrey', command=adding, font=50, pady=5)
frame3=tk.Frame(window, bg='orange', width=75, height=5)
view=tk.Button(master=frame3, text="View Entry",width=55,height=4,fg="orange",bg='lightslategrey', command=viewing, font=50, pady=5)
frame4=tk.Frame(window, bg='red', width=75, height=5)
delete=tk.Button(master=frame4, text="Delete Entry",width=55,height=4,fg="red",bg='lightslategrey', command=deleting, font=50, pady=5)
detail=tk.Button(master=window, text="View residents details \n(Not for visitors)",width=35,height=2,fg="black",bg='white', command=resdetails, font=50, pady=5)
frame1.pack()
frame2.pack()
frame3.pack()
frame4.pack()
label.pack()
add.pack()
view.pack()
delete.pack()
detail.pack()
#Close Button:
close=tk.Button(window, width=10, height=3, text="Close", bg='lavender', command=end1, pady=5)
close.pack() window.mainloop()
