
## Basic Matplotlib Plot 
- Below is an example of simple matplotlib plot using arrays 

```Python 

import matplotlib.pyplot as mp
import numpy as np

p=np.array([100,200,300])
d=np.array([10,7,5])
mp.plot(d,p,marker='o')
mp.xlabel("Demand")
mp.ylabel("Price")
mp.savefig("plot.png")

```

- Output: 
 ![[plot.png]]

- The above code utilizes the `plot()` method to plot d and b. The `xlabel` and `ylabel` is used to give graph more definition. 
- We can either use `.savefig()` method to save it or `show()` to just display it

### Making the plot clear
- To make the following plot better and more understandable, We can use markers and many more parameters on the graph
- Markers are used to highlight all the data points in the plot. Along with markers we can use line styles, line width, colors and so much more

- ## Example: 

```Python 

import matplotlib.pyplot as mp
import numpy as np

p=np.array([100,200,300])
d=np.array([10,7,5])
mp.plot(d,p,marker='o',linestyle="-",linewidth=2,markersize=15,color="red")
mp.xlabel("Demand")
mp.ylabel("Price")
mp.savefig("plot2.png")

```

- The above code creates a dashed line with width 2 with a circular marker to point the data The color can range to various other and linestyle can also have `:` for dotted line, the marker size and line width can be changed. Also there can be various shape of markers like circle, square, triangle which can be modified accordingly
- ### Output: 

![[plot2.png]]

### Color Customization plot


```Python

import matplotlib.pyplot as plt
x = [1, 2, 3, 4]

y1 = [1, 4, 9, 16]

y2 = [1, 3, 5, 7]

plt.plot(x, y1, color='red', label='Quadratic')
plt.plot(x, y2, color='#1f77b4', label='Linear')
plt.title("Color Example")
plt.xlabel("X-Axis")
plt.ylabel("Y-Axis")
plt.legend()
plt.savefig("color.png")

```

- The above code will create two plot in the graph with different graphs and the `label=""` argument is used to show the legend
- ### Output: 

![[color.png]]


### Using Grid 

- We can also add grid in the graph to make it more readable

```Python

import matplotlib.pyplot as plt
x = [1, 2, 3, 4]

y1 = [1, 4, 9, 16]

plt.plot(x, y1)

plt.title("Grid Example")

plt.grid(color="gray",linestyle="--",linewidth="0.5")

plt.savefig("simplegrid.png")

```

- The above code creates a dashed gray grid which can also be modified according to our use case
- #### Output: 

![[simplegrid.png]]

# Subplot

- With Subplot we can create various plot in a single figure. To create subplot we need to use `subplot()` method
```Python 

import matplotlib.pyplot as mp
import numpy as np
#subplot 1
a=np.array([100,200,300])
b=np.array([30,20,10])
mp.subplot(1,2,1)
mp.plot(a,b)

#subplot2
a=np.array([100,200,300])
b=np.array([10,20,30])
mp.subplot(1,2,2)
mp.plot(a,b)
mp.savefig("subplot.png")

```

- Other syntax are the same only `subplot()` method is the difference maker

- `mp.subplot()` takes three arguments, 1st the  number of rows, then the number of cols and then finally which is the position of current plot

- `mp.subplot(1,2,1)` means that the figure will have 1 row 2 columns and the current plot is the first plot
- #### Output: 
![[subplot.png]]

### Another subplot with 4 subplots 2 x 2

```Python 

import matplotlib.pyplot as mp
import numpy as np
#subplot 1
a=np.array([100,200,300])
b=np.array([30,20,10])
mp.subplot(2,2,1)
mp.plot(a,b)

#subplot2
a=np.array([100,200,300])
b=np.array([10,20,30])
mp.subplot(2,2,2)
mp.plot(a,b)

#subplot3
a=np.array([100,200,300])
b=np.array([30,30,30])
mp.subplot(2,2,3)
mp.plot(a,b)

#subplot4
a=np.array([100,200,300])
b=np.array([10,10,10])
mp.subplot(2,2,4)
mp.plot(a,b)

mp.savefig("subplotpro.png")

```

- This creates 4 plots in a figure 2 on top two on bottom
- #### Output: 

![[subplotpro.png]]

## Scatterplot

- Scatter plot is used to identify the relationship between two variables
- like over and runs increase in cricket
- instead of `plot()` we use the `scatter()` method

```Python 

import matplotlib.pyplot as mp
import numpy as np

overs=np.array([1,2,3,4,5,6,7,8,9,10])
runs=np.array([10,15,20,25,40,60,70,89,105,134])
mp.scatter(overs,runs)
mp.title("Over progress")
mp.savefig("scatter.png")

```

- #### Output

![[scatter.png]]

## Bar Graph:
- Helps to show data of categories in bars
- Useful in representing population and so on
- #### Example: 
```Python 

import matplotlib.pyplot as mp
import numpy as np

student=np.array(["Ram","Hari","Sita"])
marks=np.array([40,70,99])
mp.bar(student,marks,color="red")
mp.xlabel("Student")
mp.ylabel("Marks")
mp.title("BarGraph of various student")
mp.savefig("bargraph.png")

```

- #### Output: 

![[bargraph.png]]

- We can also create a horizontal bar by using `barh`() method instead of `bar()`
- #### Example :
```Python 

import matplotlib.pyplot as mp
import numpy as np

student=np.array(["Ram","Hari","Sita"])
marks=np.array([40,70,99])
mp.barh(student,marks,color="red")
mp.xlabel("Student")
mp.ylabel("Marks")
mp.title("BarGraph of various student")
mp.savefig("horizontalbargraph.png")

```

- ####Output: 


![[horizontalbargraph.png]]


- This is one way of doing it however in this way, the bars are of the same color and we can also have bar of different colors

- For that to happen we'd want to create a list of colors with similar number to number of data and in `color="red"` we need to do `color=colorlist`

```Python 

import matplotlib.pyplot as mp

import numpy as np

student=np.array(["Ram","Hari","Sita"])
marks=np.array([40,70,99])
bar_color=["red","yellow","purple"]
mp.bar(student,marks,color=bar_color)
mp.xlabel("Student")
mp.ylabel("Marks")
mp.title("BarGraph of various student")
mp.savefig("bargraphmulticolor.png")


```

- This way we can create a bar graph with multiple colors which is more vibrant and appealing and also easy to understand
- #### Output: 

![[bargraphmulticolor.png]]

# Histogram

- Histogram is a graphical representaton which is used to display the distribution of a dataset
- It continues data values with various frequence and it is represented in a bar graph like diagram
- Bar graph is considered with categorical data while histogram is related with numerical data
- A simple use of histogram is to represent height of 500 people 

```Python 

import matplotlib.pyplot as plt
import numpy as np

np.random.seed(42)
data = np.random.normal(50, 10, 1000) # Mean=50, StdDev=10, 1000 values
plt.hist(data, bins=20, color='skyblue', edgecolor='black')
plt.title("Histogram Example")
plt.xlabel("Value Range")
plt.ylabel("Frequency")
plt.savefig("histogramexample.png")

```

- #### Output: 

![[histogramexample.png]]


## Pie Chart

- used to show data on the proportion of total data

```Python 

import matplotlib.pyplot as plt
labels = ['Apple', 'Banana', 'Orange']
sizes = [30, 45, 25]
plt.pie(sizes, labels=labels, autopct='%1.1f%%')
plt.title("Pie Chart Example")
plt.savefig("piechart.png")

```


- labels=labels adds the label of data sets
- `autopct=%1.1f%%` formats the data and changes it to percentage containing whole value with one decimal and with percentage like 25.0%
- if it was `%1.0f%%` it would be 25% but if it was `%1.2f%%` it would be 25.00%
- #### Output: 

![[piechart.png]]

## Boxplot

- Boxplot is useful to show various statistical information in graphical manner
- A boxplot in python shows this in order : 
	- Minimum 
	- 1st Quartile 
	- Median(Q2)
	- 3rd Quartile and
	- Maximum

```Python 

import numpy as np
import matplotlib.pyplot as mp

data=np.arange(1,100,1)
mp.boxplot(data)
print(np.min(data))
print(np.percentile(data,25))
print(np.median(data))
print(np.percentile(data,75))
print(np.max(data))
mp.title("Boxplot")
mp.savefig("Boxplot.png")
```

- #### Output: 

![[Boxplot.png]]

- Here the values are : 
	 - Minimum: 1
	 - Q1: 25.5
	 - Median  50
	 - Q3: 74.5
	 - Maximum: 99
	 - Data ranges from 1-99 


