---
marp: true
theme: uncover
title: Cleaning your Data with KonMari's method
---

# Tidying Up
I wanted to share what I learned from Marie Kondo's book on tidying up and how it relates to data cleaning and creating organized databases

![bg right 50%](book.jpg)


---

For the record, I was OBSESSED with this cute, way more mature-for-her-age, quirky Japanese girl who started her own company at 18

![bg right 90%](marie_kondo_photo.jpg)

---

# Background
She found her passion at a young age in what most people think of as a chore: cleaning up.  
It was her joy, and it was something she even methodically thought about.

![bg right 90%](marie-kondo-2.avif)

---

# Why is tidying a joy?

There is a sense of contentment of having your house in-place.  To have nothing you don't like around and only the things you do.

---

# Tidying can have a positive mindset

![bg left 90%](marie-kondo-quotes.jpg)

---

# How this relates to data

![bg right 100%](statement.jpeg)

---

# Declutter first, then structure your house
- Removing noise and empty rows from your data improves quality, efficiency, and the speed of lookups in your database.  It can even improve AI and the applications that use the data.

---

# Declutter first, then structure your house

- Cleaning the data before loading into cloud storage greatly reduces the amount of storage needed and thereby the cost.  This matters when dealing with Petabytes of data; even a 1% decrease of storage can save time and cost.  
- Having the quality data off-the-bat, it's easy to know what amount of storage you really need.

---

# Declutter first, then structure your house

You do not plan to store clutter in your apartment as part of the design.  Decluttering is the first process before creating structure according to Marie Kondo.

---

## Functionality vs appearance

Marie Kondo suggests folding shirts vertically rather than stacking-on-top as seen in clothes stores.
![bg contain 100%](vertical.webp)
![bg left 100%](stacked.jpeg)

---

## Functionality vs appearance

![bg contain 100%](vertical.webp)
![bg left 100%](stacked.jpeg)

In a store, stacked shirts are nice to look at. But in a home setting, vertical clothes are easier to pull out from the drawer

---

# Functionality vs appearance
- On a similar note, should you store time as a date or a timestamp in a database?
- For end users, reading a date is nicer than reading the number of seconds passed since 1970, but in a database, timestamps are easier to process.

---

# Make your data accessible
- Winter clothes go in the cellar storage during summer.  Summer clothes in storage during winter. And old data in archives.  This leaves the rest of your data warehouses and cloud storage with only the data you regularly use.

---

# Make your data accessible
- Keys need to be accessible and close to the door where its used.  Put your data on local servers close to where your data scientists will work with them.
e.g. ETL your data to US-East on AWS if you have a team in Toronto or New York.

---

## To gain something you must discard something
- There is a Chinese saying that a full cup cannot be filled with more water
![bg right 50%](full_cup.jpeg)

---

## To gain something you must discard something
- Knowing what you want is important.  Why is it important.  You not only need to consider data, but also your spending on the storage of that data.  Where is your spending going?

---

# Tidying is a skill 
- It takes consistent practice to get good at

- Practice leads to better intuition on how to structure your house and where to put things over having profound theology.  It's the same with databases.

---

## More information
Marie Kondo's book *The Life Changing Magic of Tidying Up* has more in-depth information on her techniques, philosophy, and her KonMari method

Her bio and books are on Amazon CA [here](https://www.amazon.ca/stores/Marie-Kondo/author/B00J59XZJA?ref=ap_rdr&shoppingPortalEnabled=true)

---

# Thanks for reading

This presentation was made using [Marp](https://marp.app/), a software tool that converts markdown files to HTML and PDF.  

It can be installed as an extension in VSCode

---

# The Extra Slides

Regular expressions are useful to search for text data coming in variation

e.g. how to find customer interest in blue-gill fish in the comments section if it's written as bluegill, 
blue-gill, Bluegill, or even **BLUEGILL** (I've actually seen people write item requests in FULL CAPS)

---

# The Extra Slides
Using postgreSQL:
```sql
SELECT customer_id, comments FROM customers WHERE comments ~* 'blue[\s-]{0,1}gill';
```
the * symbol makes the comparison case-insensitive
[\s-]{0,1} captures a space, a dash, or no characters in between blue and gill

---

# The Extra Slides
RegexOne has good tutorials on regexes: [https://regexone.com/](https://regexone.com/)