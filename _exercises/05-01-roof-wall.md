---
layout: exercise
keyword: roof_wall
episode: 05-processing-data-from-fies
solution: "
~~~
filename = 'SAFI_results.csv'
fr = open(filename, 'r')

filename = 'SAFI_grass_roof_muddaub.csv'
fw1 = open(filename, 'w')

filename = 'SAFI_grass_roof_burntbricks.csv'
fw2 = open(filename, 'w')
headerline = fr.readline()
w1.write(headerline)
w2.write(headerline)
for line in fr:
   if line.split(',')[18] == 'grass' :
       if line.split(',')[19] == 'muddaub' :
           fw1.write(line)
       if line.split(',')[19] == 'burntbricks' :
           fw2.write(line)    
fr.close()
fw1.close()
fw2.close()
~~~
{: .language-python}
"
---

From the SAFI_results.csv file extract all of the records where the C01_respondent_roof_type (index 18) has a value of 'grass' and the C02_respondent_wall_type (index 19) has a value of 'muddaub' and write them to a file. Within the same program write all of the records where C01_respondent_roof_type (index 18) has a value of 'grass' and the C02_respondent_wall_type (index 19) has a value of 'burntbricks' and write them to a separate file. In both files include the header record.
