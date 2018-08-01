# acaguild-assignment-9
Assignment 9
#Read the dataset from below link

data  = urlopen("https://raw.githubusercontent.com/guipsamora/pandas_exercises/master/06_Stats/US_Baby_Names/US_Baby_Names_right.csv")

data1 = pd.read_csv("https://raw.githubusercontent.com/guipsamora/pandas_exercises/master/06_Stats/US_Baby_Names/US_Baby_Names_right.csv")

print(data1)

#Output

    Unnamed: 0       Id       Name  Year Gender State  Count
0             11349    11350       Emma  2004      F    AK     62
1             11350    11351    Madison  2004      F    AK     48
2             11351    11352     Hannah  2004      F    AK     46
3             11352    11353      Grace  2004      F    AK     44
4             11353    11354      Emily  2004      F    AK     41
5             11354    11355    Abigail  2004      F    AK     37
6             11355    11356     Olivia  2004      F    AK     33
7             11356    11357   Isabella  2004      F    AK     30
8             11357    11358     Alyssa  2004      F    AK     29
9             11358    11359     Sophia  2004      F    AK     28
10            11359    11360     Alexis  2004      F    AK     27
11            11360    11361  Elizabeth  2004      F    AK     27
12            11361    11362     Hailey  2004      F    AK     27
13            11362    11363       Anna  2004      F    AK     26
14            11363    11364    Natalie  2004      F    AK     25
15            11364    11365      Sarah  2004      F    AK     25
16            11365    11366     Sydney  2004      F    AK     25

 #Delete unnamed Columns

d = pd.DataFrame(data1)
data1.drop(data1.columns[[0]] , axis=1, inplace = True)
data1

## Show the distribution of mail and Femail

data1["Gender"].describe
print(data1["Gender"].describe())
data1[data1["Gender"] == "F"], data1[data1["Gender"] == "M"]

# Show the top 5 most preffered names

data1.head(6)

# What is the median name occurance in the dataset
data1["Name"].describe()
data1.median(axis =0)

#Distribution of male and female born count by states
pd.pivot_table(data1, index=['Gender', 'State'], aggfunc ='count')
