@startuml
entity "Members" {
+ Mid:int(10)[PK]
==
Name:varchar(50)
*Mailaddress:varchar(50)
Postcode:int(7)
Address:varchar(100)
Password:varchar(50)
}


entity "Products" {
+ PID:int(10)[PK]
==
Pname:varchar(50)
CatID:int(10)[FK]
Price:int(10)
Stock:int(10)
Company:text(30)
Overview:text(500)
}

entity "WishList"{
+ MID:int(10)[PK]
==
PID:int(10)[FK]
}

entity "Cart"{
+ MID:int(10)[PK]
==
PID:int(10)[FK]
}

entity "History"{
+ HID:int(10)[PK]
==
Hdate:date(8)
PID:int(10)[FK]
MID:int(10)[FK]
}

entity "Category"{
+ CatID:int(10)[PK]
==
* CatName:varchar(50)
}


Products --|{ Cart
Products --|{ WishList
Products --|{ History
Category --|{ Products
Members||--||WishList
Members||--||Cart
@enduml
