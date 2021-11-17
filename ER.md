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
ImgPath:varchar(30)
---default: "../ImageProductsImg/defaultImg"
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

entity "BuyLater"{
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

entity "CampSite"{
+ CSID:int(10)[PK]
==
CSIntro:varchar(300)
}

entity "FAQ"{
+ FAQID:int(10)
==
Questions:varchar(500)
Answers:varchar(800)
}

Products --|{ Cart
Products --|{ WishList
Products --|{ History
Products --|{ BuyLater
Category --|{ Products
Members--|{ History
Members||--||BuyLater
Members||--||WishList
Members||--||Cart
@enduml
