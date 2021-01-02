# python3
# List
```
bikes = ["dirt", "sports", "racer"]
first_bike = bikes[0]
last_bike = bikes[-1]

for bike in bikes:
    print(bike)
bikes.append("offroad")
```

# making squares list
```
squares = []
for x in range(1,11):
    squares.append(x**2)

squares = [x**2 for x in range(1,11)]

first_two = bikes[:2]
copy_of_bikes = bikes[:]
cp_bikes = bikes[:]
print(copy_of_bikes)
```
# delete by position
```
del copy_of_bikes[-1]
print(copy_of_bikes)
```
# delete by value first item
```
copy_of_bikes.remove("dirt")
print(copy_of_bikes)
```
# pop last item
```
print(cp_bikes)
last = cp_bikes.pop()
print("Last: " + last)
print(cp_bikes)
```
# pop first item
```
first = cp_bikes.pop(0)
print("first: " + first)
print(cp_bikes)

numbers = [1,6,3,8,2]
cp_numbers = numbers[:]
print(numbers)
print("Length: " + str(len(numbers)))
```
# sorting temporarily
```
print("Sort temporarily: " + str(sorted(numbers)))
print("Reverse temporarily: " + str(sorted(numbers, reverse=True)))
print(cp_numbers)
```
# sorting permanently
```
cp_numbers.sort()
print("Sort permanently: " + str(cp_numbers))
cp_numbers.reverse()
print("Reverse permanently: " + str(cp_numbers))

print(numbers)
print("Min: " + str(min(numbers)))
print("Max: " + str(max(numbers)))
print("Sum: " + str(sum(numbers)))

print("First three: " + str(numbers[:3]))
print("Middle three: " + str(numbers[1:4]))
print("Last three: " + str(numbers[-3:]))

name = "Ali"
print(name + " in upper " + name.upper())
print(name + " in lower " + name.lower())

x = 1
```
# conditions
```
if x == 1 : print("equal")
elif x != 1 : print("not equal")
if x > 1 :  print("greater than")
if x >= 1 : print("greater than or equal")
if x < 1 :  print("less than")
if x <= 1 : print("less than or equal")
```

# test in List
```
if "dirt" in bikes :    print("dirt is in bikes")
if "cross" not in bikes :   print("cross not in bikes")

boolean_T = True
boolean_F = False
```

# Dictionaries
```
bike = {"color": "black", "type": "sports"}
print(bike["color"])
bike["weight"] = 250
for name, value in bike.items():
    print(name + " is " + str(value))
print(bike)
print(bike.keys())
print(bike.values())
del bike["color"]
print(bike)
```
# user Input
```
name = input("what's your name? ")
print ("Hello " + str(name) + "!")
age = input("Age? ")
age = int(age)
pi = input("Pi? ")
pi = float(pi)

x = 1
while x < 3:
    print(x)
    x += 1

def add(a = 1, b = 1):
    print("a: " + str(a) + " | b: " + str(b))
    return int(a)+int(b)
print("Sum: " + str(add()))
sum = add(b = 3, a = 4)
print("Sum: " + str(sum))
```

# Classes
```
class Dog():
    def __init__(self, name):
        self.name = name
    def sit(self):
        print(self.name + " is sitting.")
my_dog = Dog("abby")
print(my_dog.name + " is a good dog.")
my_dog.sit()
```

# inheritance
```
class SADog(Dog):
    def __init__(self, name):
        super().__init__(name)
    def search(self):
        print(self.name + " is searching.")

my_search_dog = SADog("dabby")
print(my_search_dog.name + " is a search dog.")
my_search_dog.sit()
my_search_dog.search()
```

# files
```
r_filename = "add.py"
with open(r_filename) as file_object:
    lines = file_object.readlines()
for line in lines:
    print(line)

w_filename = "write_file.txt"
with open(w_filename, 'w') as file_object:
    file_object.write("Writing first line.")

with open(w_filename, 'a') as file_object:
    file_object.write("\nWriting second line.")
```

# exceptions
```
num_tickets = ""
try:
    num_tickets = int(num_tickets)
except ValueError:
    print("Please try again.")
else:
    print("Your tickets are printing.")
```
