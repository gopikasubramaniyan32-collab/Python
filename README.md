# Python
Day 1
 #To check the IP address is validate or not
 vip = input().strip()

parts = vip.split(".")

if len(parts) == 4:
    valid = True
    for part in parts:
        if not part.isdigit() or not (0 <= int(part) <= 255):
            valid = False
            break
    if valid:
        print("Valid")
    else:
        print("Invalid")
else:
    print("Invalid")
#To Validate given ISBN number
isbn = input().replace("-", "").strip()
valid = False
if len(isbn) == 10:
    s = 0
    for i in range(9):
        if not isbn[i].isdigit():
            break
        s += (i+1) * int(isbn[i])
    if isbn[9] == 'X':
        s += 10 * 10
        valid = (s % 11 == 0)
    elif isbn[9].isdigit():
        s += 10 * int(isbn[9])
        valid = (s % 11 == 0)
elif len(isbn) == 13 and isbn.isdigit():
    s = 0
    for i in range(12):
        s += int(isbn[i]) if i % 2 == 0 else 3 * int(isbn[i])
    check = (10 - (s % 10)) % 10
    valid = (check == int(isbn[12]))
print("ISBN Number is Valid" if valid else "ISBN Number is Not Valid")
#To validate the given email
import re
email = input().strip()
pattern = r'^[\w\.-]+@[\w\.-]+\.\w+$'
if re.match(pattern, email):
    print("Valid")
else:
    print("Invalid")
#To check the given string is anagram or not
a=input().strip()
b=input().strip()
if sorted(a)==sorted(b):
    print(a,"and",b,"are Anagrams.")
else:
    print(a,"and",b,"are Not Anagrams.")
#To check given string are equal or not equal
a=input()
b=input()
if sorted(a)==sorted(b):
    print("Equal")
else:
    print("Not Equal")
#To check whether a given string is Pangram or not
a=input().lower() 
for letter in "abcdefghijklmnopqrstuvwxyz":
    if letter not in a:
        print("Not Pangrams")
        break
else:
    print("Pangrams")
#To check whether the string is isogram or not
word=input().lower().strip()
if len(set(word))==len(word):
    print("ISOGRAM")
else:
    print("NOT ISOGRAM")
#Check whether it is strong or weak
password=input()
length=len(password)
u=0
l=0
n=0
s=0
if length>=8:
    for g in password:
        if g.isupper():
            u=1
        elif g.islower():
            l=1
        elif g.isdigit():
            n=1
        else:
            s=1
if(u+l+n+s==4):
    print("Strong password")
else:
    print("Weak password")
#To check whether brackets are balanced in expression
n=input()
count=0
for a in n:
    if a=='(':
        count+=1
    elif a==')':
        count-=1
    if count<0:   
        break
if count==0:
    print("Balanced")
else:
    print("Unbalanced")

    

