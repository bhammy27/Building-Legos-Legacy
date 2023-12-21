# Building-Legos-Legacy
### A historical case study using SQL and Python to discover how Lego remained a popular toy for over 7 generations

## Overview:
Over the weekend, my 6-year-old nephew and I spent a few hours playing with Legos.  As he randomly connected the multicolored bricks, I built a little car and a house.  After over an hour of stacking bricks, he then spent the rest of the afternoon playing with the car I made.  I began to wonder, how such a simple toy that my parents and I played with still popular today?  Being an inquisitive Data Analyst, I found and analyzed data which covers Lego's production from 1950-2017.

My role in this case study is that of a toy company marketing analyst.  The toy industry faces a challenge in creating toys which captivates children's interest for a month or two, let alone 7+ generations.  My direct supervisor tasked me with the challenge of analyzing Legos production trends and find any insight that we could use to create a popular generational toy.  

Using PostgreSQL and Python for visualization, the following questions will be answered:

1. What is the average number of Lego parts over total time span and per year?
2. What is the average number of Lego sets released per from 1950-2017?
3. Are there any trends with the sets produced and number of parts produced?
4. What has Lego done to create a generational toy that has remained popular for over 7 generations?

## The Data
#### An in depth description of the above ER diagram. ([source](https://rebrickable.com/downloads)):

#### inventory_parts
- "inventory_id" - id of the inventory the part is in (as in the inventories table)
- "part_num" - unique id for the part (as in the parts table)
- "color_id" - id of the color
- "quantity" - the number of copies of the part included in the set
- "is_spare" - whether or not it is a spare part

#### parts
- "part_num" - unique id for the part (as in the inventory_parts table)
- "name" - name of the part
- "part_cat_id" - part category id (as in part_catagories table)

#### part_categories
- "id" - part category id (as in parts table)
- "name" - name of the category the part belongs to

#### colors
- "id" - id of the color (as in inventory_parts table)
- "name" - color name
- "rgb" - rgb code of the color
- "is_trans" - whether or not the part is transparent/translucent

#### inventories
- "id" - id of the inventory the part is in (as in the inventory_sets and inventory_parts tables)
- "version" - version number
- "set_num" - set number (as in sets table)

#### inventory_sets
- "inventory_id" - id of the inventory the part is in (as in the inventories table)
- "set_num" - set number (as in sets table)
- "quantity" - the quantity of sets included

#### sets
- "set_num" - unique set id (as in inventory_sets and inventories tables)
- "name" - the name of the set
- "year" - the year the set was published
- "theme_id" - the id of the theme the set belongs to (as in themes table)
- num-parts - the number of parts in the set

#### themes
- "id" - the id of the theme (as in the sets table)
- "name" - the name of the theme
- "parent_id" - the id of the larger theme, if there is one


***Acknowledgments**: Rebrickable.com*

## Analysis
- From 1950 to 2017 Lego produced averaged **28698** parts per year with **2016** having the highest average with **150834** individual parts.  In **1959** Lego produced the lowest average parts with **65** parts.
- Lego produced the most sets, **713 set** in **2014**.  The **3 sets** released in **1960** marked the lowest sets relased per year.
- An interesting trend appears when comparing the yearly production vs the average production.


Lets divide the timeline into two blocks to invistagate the increased production from 1998 onward.  We will consider the time up to 1997 one block and the time after another block.
- From 1950 up to and including 1997 Lego produced an average of just over 61 sets per year. The new average sets per year is almost 1/3rd less* than the 176.9 average sets produced per year from 1950-2017.
- The average sets produced annualy from 1998 up to and including 2017 increases to **426.1**, almost 2.5 times as many average sets per year.  What created such a large increase?

### With Legos Star Wars Strikes Back!
- In 1999 Lego produced its first Star Wars themed set to take advantage of the release of Star Wars Episode 1 and resurgent popularity of the Star Wars Trilogy.
- Lego produced **635** total Star Wars sets since 1999 with over 60 sets a year released in 2012, 2014, 2016 alone. 
- During 2014, Lego released **62** sets.  That markes the most Star Wars sets released in one year.  
- The Star Wars Episode 4/5/6 edition released in 2005 has **11169** parts, making it the largest Star Wars set produced

## Recommendations to build the next generational toy
1. Create a toy that is extremely simple to play with.  Anyone can connect lego bricks.
2. Encourage the child to use their creativity and create a toy, such as a car, that they can play with when they become bored stacking bricks.
3. Create an timeless toy which can be connected to pop culture trends such as movies and tv shows.  
