# ATM Similator

## Main Menu
```md
    -----------MENU-----------
    [A] Admin   : Login
    [1] Cips    : 1.0 $
    [2] Cola    : 1.5 $
    [3] Popcorn : 2.0 $
    [4] Coffe   : 2.5 $
 ```
 ## Phone Number Menu
 ```md
     -----------Phone-----------
     [1] Error  : +9945687567
     [2] Zed    : +9948975634
 ```
 
 ## Admin Login Password :
 ```md
    pasw = "123456789"
```
## Workers

```md
Error : Repairman
Zed   : Manager 
```

# Code Explaination

## Menu Fuction
```py
def menu():
    os.system("clear")
    print(f"""{bcolors.OK}
    -----------MENU-----------
    [A] Admin   : Login
    [1] Cips    : 1.0 $
    [2] Cola    : 1.5 $
    [3] Popcorn : 2.0 $
    [4] Coffe   : 2.5 $
    """)
```
## Phone Funtion
```py
def phone(number):
    os.system("clear")
    if number== "+9945687567" or number == "1" :
        name=input(Fore.BLUE+"[Error] Hello whats your name : ")
        print(Fore.BLUE+"[Error] What You Want :")
        mes1 = input(Fore.CYAN+f"[{name}] : ")
        print(Fore.BLUE+"[Error] Ok I am calling ZED , who is the our manager...")
        time.sleep(2)
        phone("+9948975634")
    elif number == "+9948975634" or number =="2":
        print(Fore.BLUE+"[Zed] Hello , We found the problem. You can only select something that is on the menu. Please try again. Now we direct you to the menu... Please wait 10 seconds...")
        time.sleep(10)
        buy()
```

## Admin Menu
```py
def adminm(admin):
    if admin == True :
        os.system("clear")
        print(f"""{bcolors.OK}
        -----------MENU-----------
        [1] + 
        [2] -
        """)
```
## Buy (Main Function)
```py

def buy():
    menu()
    c = input(f"{bcolors.FAIL}[+] Please enter your choice  : ")
    para = int(input(f"{bcolors.FAIL}[+] Please enter your balance : "))

    cips    = 1.0
    cola    = 1.5
    popcorn = 2.0
    coffe   = 2.5
    pasw = "123456789"
    admin = False

    print("")
    if c == "1":
        para =para-cips
        #time.sleep(2)
    elif c == "2":
        para =para-cola
    elif c == "3":
        para =para-popcorn 
    elif c == "4":
        para-=coffe
    elif c == "A" or c == "a" :
        lpas = input("[+] Please enter your pasword : ")

        if pasw == lpas :
            print("[+] Correct password...")
            time.sleep(2)
            admin = True
            adminm(admin)
            d = input(f"{bcolors.OK}[+] Please enter your choice  : ")
            if d == "1":
                plus = int(input(f"{bcolors.FAIL}[+] How much you want to plus : "))
                cips = cips+plus 
                cola = cola+plus
                popcorn=popcorn+plus
                coffe=coffe+plus
                print(f"{bcolors.OK}[+] Cips    : {cips}")
                print(f"{bcolors.OK}[+] Cola    : {cola}")
                print(f"{bcolors.OK}[+] Popcorn : {popcorn}")
                print(f"{bcolors.OK}[+] Coffe   : {coffe}")
            elif d == "2":
                 minus = int(input(f"{bcolors.FAIL}[+] How much you want to minus : "))
                 cips = cips-minus 
                 cola = cola-minus
                 popcorn=popcorn-minus
                 coffe=coffe-minus
                 print(f"{bcolors.OK}[+] Cips    : {cips}")
                 print(f"{bcolors.OK}[+] Cola    : {cola}")
                 print(f"{bcolors.OK}[+] Popcorn : {popcorn}")
                 print(f"{bcolors.OK}[+] Coffe   : {coffe}")
    else:
        os.system("clear")
        print(Fore.CYAN+"""
        -----------Phone-----------
        [1] Error  : +9945687567
        [2] Zed    : +9948975634
        """)
        number = input(f"{bcolors.FAIL}[+] Some error accured... Please enter a number : ")
        phone(number)
        

    
    print(" ")
    print(f"{bcolors.FAIL}[+] Your new balance : ",para)
```
