# olympic_dataset-_using_pandas_python

dataset: https://github.com/KeithGalli/complete-pandas-tutorial/tree/master/data

Data cleaning and Visualization using pandas in python

The dataset contain some rows that were empty, so i had to           
(1) Sort the main dataset by selecting athlete that their hight is above 190cm (Height is advantage in some olympic games) saved the new file as cleaned_row.csv.  
```python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
df = pd.read_csv('./data/bios.csv')
new=df[df['height_cm'] > 190]
print(new)
new.to_csv('./data/cleaned_row.csv', index=False)
```
(2) Cleaned the sorted excel file data by selecting the empty row and filling it with N/A and saved the new file as latest_row.csv
```python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
df = pd.read_csv('./data/cleaned_row.csv')
df.shape
new = df.dropna(how='all').fillna('N/A')
new.to_csv('latest_row.csv', index=False , na_rep='N/A')
```
(3) The lastest excel cleaned dataset is filtered by selecting the country (CUBA) where the althlete are giving birth to, to know how many althlete is from CUBA that is above 190 cm in height and the generted excel file is saved for analysis. 90 althletes from CUBA met the criteria. 
```python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
df = pd.read_csv('./data/latest_row.csv')
new=df[df['born_country'].str.contains('CUB')]
print(new)
new.to_csv('databeforeplot_row.csv', index=False , na_rep='N/A')
```
(4) The final generated excel file is now used to generate a visualization to show the graphical representaion of the final dataset
```python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
df = pd.read_csv('./data/databeforeplot_row.csv')
print(df)
df[['name', 'height_cm']].plot(title="BIRTH LOCATION = CUBA",xlabel='Name', ylabel='Height_cm')
```
      
(5) Kindly view the graphical representation of the final dataset. The althletes names can be viewed from the excel file (databeforeplot_row.csv)  
<img width="572" height="455" alt="visual_cuba" src="https://github.com/user-attachments/assets/2e5288a0-f7bb-48c2-ad58-5121d1b10e53" />










