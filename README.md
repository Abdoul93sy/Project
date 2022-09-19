# Project
Training in Python


def area_calc(wall_height, wall_width):
    wall_area = wall_height * wall_width
    return wall_area
print("Welcome to the WALL PAINTING CALCULATOR.\n")
coats = float(input("Number of Coats: "))
height = float(input("Wall Height: "))
width = float(input("Wall Width: "))

total = 0
gallon = 400
num_gallon = 0
wall_area = area_calc(height, width)
total = wall_area

print("Number of rooms: ")
while True:


  room = input("is there another room you would like to paint? Y/N\n").lower()

  if room == "y":
    room_height = float(input("room Height: "))
    room_width = float(input("room Width: "))
    room_lenght = float(input("room length: "))
    surfaceArea = 2 * (room_height*room_lenght + room_height*room_width + room_lenght * room_width)
    total += surfaceArea

  else:
    print(f"Your total area is: {total} sqft.")
   
    num_gallon = (total / gallon ) * coats 
    print(f"You will need {num_gallon} gallons of paint.")
    break
    

paint_cost = 30  # $30/gallon
distance = .55 # .55/mile
members_discount = 25/100 # 25% per members only
total1= True
total_member_pickup = 0
total_nonmember_pickup = 0
total_member_delivery  = 0
total_nonmember_delivery = 0



delivery = input("if you want pick-up? Y/N\n").lower()
    

if delivery == "y":
    member = input ("are you a member? ")
    if member == "y":
        total_member_pickup = (num_gallon * paint_cost ) * (1-members_discount)
        print (f"your total cost {total_member_pickup:.2f}")
    else:    
        total_nonmember_pickup = num_gallon * paint_cost
        print (f"your pickup total:{total_nonmember_pickup:.2f}")
elif delivery == "n":
    member = input ("are you a member? ")
    distance = float(input("enter your delivery distance from our location in miles: "))
    if member == "y":
        total_member_delivery = (((num_gallon* paint_cost)*distance)*(1-members_discount))
        print(f"your delivery cost: {total_member_delivery:.2f} ")
    else: 
        total_nonmember_delivery = num_gallon * paint_cost * distance
        print (f"your total delevery cost {total_nonmember_delivery:.2f}" )
