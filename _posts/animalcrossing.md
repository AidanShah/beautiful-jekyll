---
layout: post
title: Animal Crossing Lab
subtitle: Lab 2
thumbnail-img: 
tags: [Lab]
comments: true
---

**Socks?**

  This lab was about pulling data from an Animal Crossing API and using it to answer a couple of questions.
The data was collected by a bunch of people on the internet.
  
  The first task was to use the API to generate a csv that we could then analyze. Below you can see my code:
~~~
import requests
BASE_URL = "https://hm-cs.herokuapp.com" 
ENDPOINT = "/socks"
API_KEY = "ArtOfDataKEY123" 
n = 0
with open('data/animal_crossing.csv', 'w') as f:
    payload = {'key': API_KEY, 'idx': n}
    response = requests.get(BASE_URL+ENDPOINT, params=payload)
    while response.ok:
        data = response.text
        n += 1
        f.write(str(data) + "\n")
        payload = {'key': API_KEY, 'idx': n}
        response = requests.get(BASE_URL+ENDPOINT, params=payload)
    else:
        print(response.status_code, response.text)
~~~
Using the requests module my code prints the response it gets from the API to the csv animal_crossing.csv. First it sets the base url, endpoint, and API key as variables so I can reference then later. Then it creates the csv and opens it. Afterwards it makes the first request using index 0. The indices refer to the rows in the original spreadsheet. Because I didn't know the size of the spreadsheet, and it could change, I used a while loop to keep getting the repsonses as long as they don't print errors. So I needed the first response outside the while loop to satisfy the while condition. Inside the while loop the code writes the response to a variable as a string of comma separated values, prints this to the csv, and then gets the next response. At first I put the response before the printing put then it put an error message into the csv because the index for the last line was out of the range of the API.

  For the next two questions I tried to use classes. So I created a sock class shown below. I recognized that this was similar to some of the stuff we did in the digimon lab, but wanted to do it using classes because we had just learned about them and I thought they could be a useful tool.

~~~
class Sock: 
    def __init__(self, name, csv_name):
        self.name = name
        self.variations = []
        self.colors = [] 
        with open(csv_name, 'r') as f: 
            data = csv.DictReader(f)
            for row in data:
                if row['\ufeffName'] == name:
                    self.variations.append(row['Variation'])
                    if row['Color 1'] not in self.colors:
                        self.colors.append(row['Color 1'])
                    if row['Color 2'] not in self.colors:
                        self.colors.append(row['Color 2'])
    def countVariation(self): 
        return len(self.variations)
~~~

This class is fairly straightfoward as it only has a constructor and a simple function. The class takes a csv and name of sock. Then it finds all the variations and colors from the csv by checking the name inputted against that of each row of the csv and inputting the correct data if the names match. The only function in the class just returns the length of variations to get how many variations the sock has.
 
  To find which sock had the most variations I wrote the following code.
~~~
with open('data/animal_crossing.csv','r') as f: 
    data = csv.DictReader(f)
    variations = 0
    names = []
    for row in data:
        s = Sock(row['\ufeffName'], 'data/animal_crossing.csv')
        if s.countVariation() > variations: 
            variations = s.countVariation()
            names = [s.name]
        elif s.countVariation() == variations and s.name not in names:
            names.append(s.name)
    print(names)
~~

This code first opens the csv. Then it creates a bunch of variables. data is the variable that stores the csv as a dict reader, names is a list that will keep track of what sock has the most variations, and socks is a list that keeps track of the socks that have already been tried. Next the code goes row by row through the data set and for each row creates a sock object. This is the first sign that using classes was a bad idea. The way I have this structured, the code creates a class for every row. But remember in the constructor of the class it also goes through every row of the dataset. This makes the code take way longer to run than it should. After the class was created, using the countVariation function, the code checks if the number of variations of this sock is the highest so far. If it is then it replaces whatever was in names and sets variations to its number of variations. If it has equal variations to the highest and is not a sock that has been checked before the sock name gets added to names. The socks that had the most variations were Argyle Crew Socks, Color-blocked Socks, Frilly Knee-high Socks, Holey Tights, Kiddie Socks, Mixed-tweed Socks, No-show Socks, Semi-opaque Socks, Semi-opaque Tights, Sequin Leggings, Simple-accent Socks, Striped Socks, Striped Tights, Tube Socks, Ultra no-show Socks, Vivid Leggings, Vivid Socks, and Vivid tights with 8 variations each.

  Finally we needed to find how many socks of each color there were. For this question I counted each sock variation as a different sock. This was a disaster. I had made a sock class so that I could answer both questions quickly, easily, and in a way that was easy to understand. When I got to this point I tried to use the sock class to answer the question, but every way I thought of was more complicated then just doing it separately. I have provided my code below. Note: this code and the code for the previous question are combined in the actual file but were separated to be easier to understand.

~~~
with open('data/animal_crossing.csv','r') as f: 
    data = csv.DictReader(f)
    socks = []
    colorsOfSocks = {}
    for row in data:
        if row['Color 1'] not in colorsOfSocks: 
            colorsOfSocks[row['Color 1']] = 1
            socks.append(row['\ufeffName'])
        else:
            colorsOfSocks[row['Color 1']] += 1
        if row['Color 1'] != row['Color 2']:
            if row['Color 2'] not in colorsOfSocks:
                colorsOfSocks[row['Color 2']] = 1
                socks.append(row['\ufeffName'])
            else:
                colorsOfSocks[row['Color 2']] += 1
    print(colorsOfSocks)
~~~~

The code starts the same as the last; it creates the output variable and the variable that keeps track of the rows that have already been done then loops throuhg the dataset row by row. Then it checks if the first color of the sock is in the dictionary. If it is, the code adds one to that colors count. If it is not, the code adds the color as a key and sets its value as 1. Then it checks if the second color is the same as the first. If it isn't then it runs the same code as if it were the first color.  If the colors are the same it doesn't do anything. There were 85 white socks, 41 pink socks, 39 red socks, 50 green socks, 33 light blue socks, 27 orange socks, 37 purple socks, 47 blue socks, 33 yellow socks, 15 beige socks, 59 black socks, 11 brown socks, 31 gray socks, and 14 colorful socks.

Image Sources:
https://www.idownloadblog.com/2017/11/21/animal-crossing-pocket-camp-hits-app-store/
