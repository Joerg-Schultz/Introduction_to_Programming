

Now, that you have learned about Classes and Inheritance, it is about time you put that freshly acquired knowledge to good use.

## Introduction
Old MacDonald not only has a farm, he now also has a computer and some knowledge of Kotlin! So naturally Farmer MacDonald wants to implement a virtual farm, which lets him keep track of his animals (Cows, sheep, Alpacas or comodo dragons) and their needs as well as the business aspects of his farm.
To keep the Farm running, he needs to feed the animals, check their health status and breed the animals to create new stock (either to replace lost animals or to sell them). But he also needs to buy the supplies to keep his animals happy.

## The task
In this exercise, you’re supposed to implement a simple farm with a variety of different animals. Since Old MacDonald is a very capitalistic farmer, he seeks to grow his business and sell his animals.
So, your first basic task is to implement a Farm-class and different species of animals, which inherit from an Animal-class. Small hint: The different “barns” can simply be lists of the animals :wink:.
All animals share data like “age”, “health”, “sex”, “diet”, “size” or functions like<span style="color:blue">Eat() , Sleep(), Shout()</span>  but differ in other aspects. A Monkey has an additional function <span style="color:blue">Climb()</span> or a Bird a function <span style="color:blue">Fly()</span> . 
A cows <span style="color:blue">Shout()</span>.-Function should return “Moooo!”, whereas a pigs Shout()-Function should return “Oink!”
<br>

The farm starts off with 10 Individuals in each barn. To breed the animals, you need to check their compatibility, meaning their species, their sex and their health status. Full health = 100. If one of the animals’ health is below 50, breeding will not be successful.
If breeding was successful, however, a new Animal of the given species is added to the barn. After breeding, the parents’ health is reduced by 20 points. To restore health points, the animals need to be fed, or they need to Sleep(). 
</br>

To solve this, just turn to the Atomic Kotlin exercises for inspiration :-)

## Optional

Now, you can take this a few steps further and create your own little Farm-Simulator:

Here are a few ideas:

1) The farm has a starting budget of 100 000 Kotlin-Dollars and 300kg of Food in stock.
2) The market price for any new Animal is 1000 Kotlin-Dollars
3) 25kg of plant food costs about 20 Kotlin-Dollars. Carnivore food is about 10K$ per KG
4) Different animals consume different amounts of food in a day (small animals: 5 kg, medium: 10 kg, big: 15kg)
5) Which properties are shared by all the animals on the farm? Which are special to different species? Sounds like “Inheritance” could be of use here :wink:. There are different sizes, and different diets. (Cow: big, vegetarian; Comodo dragon: medium, carnivore)

6) To Add Animals to your farm, you can either buy new ones or breed animals on your farm. In the first case, you need a function Buy(), which takes the quantity and type of the desired animal and adds them to your farm, while deducting the price from your budget. Maybe you can think about a dedicated market class?
7) You can generate money by selling animals. Older animals however, bring less income than young ones. Also: Young animals have a higher fertility rate than old ones.

8) Oh, and of course you could collect these data and plot them later on interactively on your android-phone :-)