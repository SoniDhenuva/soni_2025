---
layout: page
title: About
permalink: /about/
---

## Intro
<p>Hi, My name is Sonika Dhenuva Konda, I go by Soni. I am in 10th grade and 15 years old.</p>
<p>I joined a few clubs at school like Robotics & Debate. I also own my own small buisness of selling jewlry</p>

## My Favorites
<p>My favorite food is icecream, i also love any type of chocolate</p>
<p>I also have several favorite movie such as all Ironman, Deadpool, Spiderman, Sherlock Homes, Transformers, Rush Hour, Jurrasic World, etc</p>
<img src="{{site.baseurl}}/images/jurassic.png">
<img src="{{site.baseurl}}/images/deadpool.png">
<img src="{{site.baseurl}}/images/spiderman.png">


## My Family
<p>Fun Fact! I was actually born in india. I moved here when I was 9 months old. My dad and mom are both from India, and I have a younger sister who is 9.</p>
<p> A lot of my family, including grandparents, aunts, uncles, and cousin are in Indian and love to go and visit then once in a few years!</p>
<img src="{{site.baseurl}}/images/india.png">
<img src="{{site.baseurl}}/images/food.png">




# Github Pages Playground
<p>This is the Github Playground w/ Games</p>
{%include nav/github_pages.html %}







# FrontEnd Devolpment
<html> 

<div style="border:dashed" > 
<h2 color="white"> HELLO </h2>
<p> Soni Dhenuva </p>
<br>
<button id="myButton">Dont Click this.</button>
<p id="responseMessage"></p>
<script src="script.js"></script>
</div>


<script>
const button = document.getElementById('myButton');
const message = document.getElementById('responseMessage');
// Add an event listener to the button for the click event
button.addEventListener('click', function() {
    // Change the message when the button is clicked
    message.textContent = "I will find you";
});
</script>






<div style="border:dashed"> 
<a href="https://sallysbakingaddiction.com/strawberry-cake/"> Strawberry Cake Recipie</a>
<br>

<a href="https://sallysbakingaddiction.com/the-great-pumpkin-pie-recipe/">Pumpkin Pie Recipie</a>
<br>
<p> Which recipe do like better? </p>
</div>

</html>

# Playing with Jupyter Notebooks and Python

## Emoji Playground
<script>
from emoji import emojize 
print(emojize(":thumbs_up: Python is awesome! :grinning_face:"))
</script>

## Extracting Data

<script>
from newspaper import Article
from IPython.display import display, Markdown


urls = ["http://cnn.com/2023/03/29/entertainment/the-mandalorian-episode-5-recap/index.html", 
        "https://www.cnn.com/2023/06/09/entertainment/jurassic-park-anniversary/index.html"]

for url in urls:
    article = Article(url)
    article.download()
    article.parse()
    # Jupyter Notebook Display
    # print(article.title)
    display(Markdown(article.title)) # Jupyter display only
    display(Markdown(article.text)) # Jupyter display only
    print("\n")

import wikipedia 
from IPython.display import display, Markdown # add for Jupyter

terms = ["Python (programming language)", "JavaScript"]
for term in terms:
    # Search for a page 
    result = wikipedia.search(term)
    # Get the summary of the first result
    summary = wikipedia.summary(result[0])
    print(term) 
    # print(summary) # console display
    display(Markdown(summary)) # Jupyter display
</script>

## Inpecting a function
<script>
import inspect 
from newspaper import Article

# inspect newspaper Article function
print(inspect.getsource(Article))
</script>

## Python Data Types
<script>
import sys
from typing import Union

# Define types for mean function, trying to analyze input possibilities
Number = Union[int, float]  # Number can be either int or float type
Numbers = list[Number] # Numbers is a list of Number types
Scores = Union[Number, Numbers] # Scores can be single or multiple 

def mean(scores: Scores, method: int = 1) -> float:
    """
    Calculate the mean of a list of scores.
    
    Average and Average2 are hidden functions performing mean algorithm

    If a single score is provided in scores, it is returned as the mean.
    If a list of scores is provided, the average is calculated and returned.
    """
    
    def average(scores): 
        """Calculate the average of a list of scores using a Python for loop with rounding."""
        sum = 0
        len = 0
        for score in scores:
            if isinstance(score, Number):
                sum += score
                len += 1
            else:
                print("Bad data: " + str(score) + " in " + str(scores))
                sys.exit()
        return sum / len
    
    def average2(scores):
        """Calculate the average of a list of scores using the built-in sum() function with rounding."""
        return sum(scores) / len(scores)

    # test to see if scores is  a list of numbers
    if isinstance(scores, list):
        if method == 1:  
            # long method
            result = average(scores)
        else:
            # built in method
            result = average2(scores)
        return round(result + 0.005, 2)
    
    return scores # case where scores is a single valu

# try with one number
singleScore = 100
print("Print test data: " + str(singleScore))  # concat data for single line
print("Mean of single number: " + str(mean(singleScore)))

print()

# define a list of numbers
testScores = [90.5, 100, 85.4, 88]
print("Print test data: " + str(testScores))
print("Average score, loop method: " + str(mean(testScores)))
print("Average score, function method: " +  str(mean(testScores, 2)))

print()

badData = [100, "NaN", 90]
print("Print test data: " + str(badData))
print("Mean with bad data: " + str(mean(badData)))
</script>

