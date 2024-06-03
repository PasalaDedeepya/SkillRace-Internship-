 [Dedeepya-skillrace task1.txt](https://github.com/user-attachments/files/15536136/Dedeepya-skillrace.task1.txt)
                                                                  
                                                                  SkillRace Internship
                                                                         Phase 1

 Task 1a:
      
i)Please write a program to generate all sentences where subject is in ["I", "You"]and verb is in ["Play", "Love"] and the object is in ["Cricket","Ludo"].

Source Code:

import random

subject = ['I','You']
verb = ['love','play']
Object = ['cricket','ludo']
sub = random.choice(subject)
Verb = random.choice(verb)
Obj = random.choice(Object)
print(sub,Verb,Obj)

Output:

You play ludo
​I love ludo
I love cricket
You play cricket

ii) Convert emoji into text in Python - Converting emoticons or emojis into textin Python can be done using thedemoji module. It is used to accurately removeand replace emojis in text strings.

Source code:

import demoji
text = input("enter emoji's : ")
demoji.findall(text)

Output:

enter emoji's : 😍🫂🍔🍕❤️☮
{'🍕': 'pizza',
 '❤️': 'red heart',
 '😍': 'smiling face with heart-eyes',
 '🫂': 'people hugging',
 '☮': 'peace symbol',
 '🍔': 'hamburger'}
 
 Task 1b:

i)Design a ‘book’ class with title, author, publisher, price and author’s royalty asinstance variables. Provide getter and setter properties for all variables. Alsodefi ne a method royalty() to calculate royalty amount author can expect toreceive the following royalties:10% of the retail price on the   first 500 copies; 12.5%for the next 1,000 copies sold, then 15% for all further copies sold. Then design anew ‘ebook’ class inherited from ‘book’ class. Add ebook format (EPUB,PDF,MOBI etc) as additional instance variable in inherited class. Override royalty() method to deduct GST @12% on ebooks.

Source Code:

class Book:
    def _init_(self, title, author, publisher, price):
        self._title = title
        self._author = author
        self._publisher = publisher
        self._price = price
        self._royalty = None

    # Getter and setter properties for title
    @property
    def title(self):
        return self._title

    @title.setter
    def title(self, value):
        self._title = value

    # Getter and setter properties for author
    @property
    def author(self):
        return self._author

    @author.setter
    def author(self, value):
        self._author = value

    # Getter and setter properties for publisher
    @property
    def publisher(self):
        return self._publisher

    @publisher.setter
    def publisher(self, value):
        self._publisher = value

    # Getter and setter properties for price
    @property
    def price(self):
        return self._price

    @price.setter
    def price(self, value):
        self._price = value

    # Calculate author's royalty
    def calculate_royalty(self, copies_sold):
        if copies_sold <= 500:
            self._royalty = 0.10 * self._price * copies_sold
        elif 500 < copies_sold <= 1500:
            self._royalty = 0.125 * self._price * copies_sold
        else:
            self._royalty = 0.15 * self._price * copies_sold

        return self._royalty

# Example usage
book1 = Book("The Great Gatsby", "F. Scott Fitzgerald", "Penguin", 25.99)
copies_sold = 1000
royalty_amount = book1.calculate_royalty(copies_sold)
print(f"Author's royalty for {copies_sold} copies sold: ${royalty_amount:.2f}")


Output:

Author's royalty for 1000 copies sold: $3248.75


ii) Implement simple FLAMES game using Python.


Source Code:

def calculate_flames(name1, name2):
    name1 = name1.lower().replace(" ", "")
    name2 = name2.lower().replace(" ", "")

    for char in name1:
        if char in name2:
            name1 = name1.replace(char, "", 1)
            name2 = name2.replace(char, "", 1)

    total_length = len(name1) + len(name2)
    flames = ["Friends", "Love", "Affection", "Marriage", "Enemies", "Siblings"]

    while len(flames) > 1:
        split_index = (total_length % len(flames) - 1)
        if split_index >= 0:
            right = flames[split_index + 1:]
            left = flames[:split_index]
            flames = right + left
        else:
            flames = flames[:-1]

    return flames[0]

name1 = input("Enter the first name: ")
name2 = input("Enter the second name: ")

result = calculate_flames(name1, name2)
print(f"Relationship between {name1} and {name2} is: {result}")

Output:

Enter the first name: siddarth malhotra
Enter the second name: kiara advani
Relationship between siddarth and kiara advani is: Marriage
