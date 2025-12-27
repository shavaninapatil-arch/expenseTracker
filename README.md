# Expenses Tracker project
expensesList=[] # List of expenses in form of Dictionary
print("Welcome to expenses Tracker")

while True:
    print("=====MENU=====")
    print("1.Add Expenses:")
    print("2.View all Expenses:")
    print("3.View Total Expenses")
    print("4.Exit")

    choice=int(input("Please Enter your Choice:"))

    #Add Expenses
    if (choice==1):
        date=input("Enter the date for your expenses:")
        category=input("Enter the category in which you have expenses(Travel,food,etc):")
        description=input(" Give some more details:")
        amount=float(input("Enter the amount:"))

        expense={
            "date":date,
            "category":category,
            "description":description,
            "amount":amount
        }
        expensesList.append(expense)
        print("/n AND WE ARE DONE")

        #VIEW ALL EXPENSE
    elif(choice==2):
        if(len(expensesList)==0):
            print("NO EXPENSES")
        else:
            print("THIS IS ALL YOUR EXPENSE")
            count=1
            for eachexpense  in expensesList:
                print(f"Expenses Number{count}-> {eachexpense["date"]},{eachexpense["category"]},{eachexpense["description"]},{eachexpense["amount"]}")
                count=count+1

    # VIEW TOTAL SPENDING
    elif(choice==3):
        total=0
        for eachexpense in expensesList:
            total =total + eachexpense["amount"]
        print("\n TOTAL EXPENSES=",total)

    # EXIT
    elif(choice==4):
        print("THNAK YOU!!! FOR USING THIS SOFTWARE")
        break
    else:
        print("INVALID CHOICE:TRY AGAIN")
