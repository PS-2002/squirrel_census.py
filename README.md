# squirrel_census.py
#To find the popiulation of all the squrrels living in the park on the basis of their fur color.
import pandas
data = pandas.read_csv("2018_Central_Park_Squirrel_Census_-_Squirrel_Data.csv")
gray_squirrel_count = len(data[data["Primary Fur Color"] == "Gray"])
print(gray_squirrel_count)
red_squirrel_count = len(data[data["Primary Fur Color"] == "Cinnamon"])
print(red_squirrel_count)
black_squirrel_count = len(data[data["Primary Fur Color"] == "Black"])
print(black_squirrel_count)


data_dict = {
    "Primary Fur Color": ["Gray", "Red", "Black"],
    "Squirrel Count": [gray_squirrel_count, red_squirrel_count, black_squirrel_count]
}
data = pandas.DataFrame(data_dict)

data.to_csv("squirrel_count.csv")
