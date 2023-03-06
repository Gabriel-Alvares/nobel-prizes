```python
import requests
import pandas as pd
import io

url =   'http://api.nobelprize.org/2.1/nobelPrizes?limit=10000&nobelPrizeYear=1901&yearTo=2022&format=csv&csvLang=en'

headers = {'accept': 'application/csv'}

response = requests.get(url, headers=headers)

# Carrega a resposta como um objeto de dataframe do pandas
df = pd.read_csv(io.StringIO(response.content.decode('utf-8')))

print(df)
```

                            category  year                          id name share  \
    Chemistry                   1901   160      Jacobus H. van 't Hoff    1   NaN   
    Literature                  1901   569             Sully Prudhomme    1   NaN   
    Peace                       1901   462                Henry Dunant  1/2   NaN   
    Peace                       1901   463              Frédéric Passy  1/2   NaN   
    Physics                     1901     1      Wilhelm Conrad Röntgen    1   NaN   
    ...                          ...   ...                         ...  ...   ...   
    Peace                       2022  1020  Center for Civil Liberties  1/3   NaN   
    Physics                     2022  1012                Alain Aspect  1/3   NaN   
    Physics                     2022  1013                John Clauser  1/3   NaN   
    Physics                     2022  1014             Anton Zeilinger  1/3   NaN   
    Physiology or Medicine      2022  1011                Svante Pääbo    1   NaN   
    
                                                            overallmotivation  \
    Chemistry               in recognition of the extraordinary services h...   
    Literature              in special recognition of his poetic compositi...   
    Peace                   for his humanitarian efforts to help wounded s...   
    Peace                   for his lifelong work for international peace ...   
    Physics                 in recognition of the extraordinary services h...   
    ...                                                                   ...   
    Peace                   The Peace Prize laureates represent civil soci...   
    Physics                 for experiments with entangled photons establi...   
    Physics                 for experiments with entangled photons establi...   
    Physics                 for experiments with entangled photons establi...   
    Physiology or Medicine  for his discoveries concerning the genomes of ...   
    
                            motivation  
    Chemistry                      NaN  
    Literature                     NaN  
    Peace                          NaN  
    Peace                          NaN  
    Physics                        NaN  
    ...                            ...  
    Peace                          NaN  
    Physics                        NaN  
    Physics                        NaN  
    Physics                        NaN  
    Physiology or Medicine         NaN  
    
    [989 rows x 7 columns]
    


```python
df.to_csv('dados.csv', index=True)

```


```python
prizes = pd.read_excel('arquivos/Prizes.xlsx')
```


```python
print(dados_corrigido)
```

                      category  year   id                            name  \
    0                Chemistry  1901  160          Jacobus H. van 't Hoff   
    1               Literature  1901  569                 Sully Prudhomme   
    2                    Peace  1901  462                    Henry Dunant   
    3                    Peace  1901  463                FrÃ©dÃ©ric Passy   
    4                  Physics  1901    1         Wilhelm Conrad RÃ¶ntgen   
    5   Physiology or Medicine  1901  293                Emil von Behring   
    6                Chemistry  1902  161                    Emil Fischer   
    7               Literature  1902  571                 Theodor Mommsen   
    8                    Peace  1902  464                  Ã‰lie Ducommun   
    9                    Peace  1902  465                    Albert Gobat   
    10                 Physics  1902    2              Hendrik A. Lorentz   
    11                 Physics  1902    3                   Pieter Zeeman   
    12  Physiology or Medicine  1902  294                     Ronald Ross   
    13               Chemistry  1903  162                Svante Arrhenius   
    14              Literature  1903  572         BjÃ¸rnstjerne BjÃ¸rnson   
    15                   Peace  1903  466                   Randal Cremer   
    16                 Physics  1903    4                 Henri Becquerel   
    17                 Physics  1903    5                    Pierre Curie   
    18                 Physics  1903    6                     Marie Curie   
    19  Physiology or Medicine  1903  295             Niels Ryberg Finsen   
    20               Chemistry  1904  163              Sir William Ramsay   
    21              Literature  1904  573              FrÃ©dÃ©ric Mistral   
    22              Literature  1904  574                 JosÃ© Echegaray   
    23                   Peace  1904  467  Institute of International Law   
    24                 Physics  1904    8                   Lord Rayleigh   
    25  Physiology or Medicine  1904  296                     Ivan Pavlov   
    26               Chemistry  1905  164                Adolf von Baeyer   
    27              Literature  1905  575              Henryk Sienkiewicz   
    28                   Peace  1905  468              Bertha von Suttner   
    29                 Physics  1905    9                  Philipp Lenard   
    30  Physiology or Medicine  1905  297                     Robert Koch   
    
                      share  overallmotivation  \
    0                     1                NaN   
    1                     1                NaN   
    2   2023-02-01 00:00:00                NaN   
    3   2023-02-01 00:00:00                NaN   
    4                     1                NaN   
    5                     1                NaN   
    6                     1                NaN   
    7                     1                NaN   
    8   2023-02-01 00:00:00                NaN   
    9   2023-02-01 00:00:00                NaN   
    10  2023-02-01 00:00:00                NaN   
    11  2023-02-01 00:00:00                NaN   
    12                    1                NaN   
    13                    1                NaN   
    14                    1                NaN   
    15                    1                NaN   
    16  2023-02-01 00:00:00                NaN   
    17  2023-04-01 00:00:00                NaN   
    18  2023-04-01 00:00:00                NaN   
    19                    1                NaN   
    20                    1                NaN   
    21  2023-02-01 00:00:00                NaN   
    22  2023-02-01 00:00:00                NaN   
    23                    1                NaN   
    24                    1                NaN   
    25                    1                NaN   
    26                    1                NaN   
    27                    1                NaN   
    28                    1                NaN   
    29                    1                NaN   
    30                    1                NaN   
    
                                               motivation  
    0   in recognition of the extraordinary services h...  
    1   in special recognition of his poetic compositi...  
    2   for his humanitarian efforts to help wounded s...  
    3   for his lifelong work for international peace ...  
    4   in recognition of the extraordinary services h...  
    5   for his work on serum therapy especially its a...  
    6   in recognition of the extraordinary services h...  
    7   the greatest living master of the art of histo...  
    8   for his untiring and skilful directorship of t...  
    9   for his eminently practical administration of ...  
    10  in recognition of the extraordinary service th...  
    11  in recognition of the extraordinary service th...  
    12  for his work on malaria by which he has shown ...  
    13  in recognition of the extraordinary services h...  
    14  as a tribute to his noble magnificent and vers...  
    15  for his longstanding and devoted effort in fav...  
    16  in recognition of the extraordinary services h...  
    17  in recognition of the extraordinary services t...  
    18  in recognition of the extraordinary services t...  
    19  in recognition of his contribution to the trea...  
    20  in recognition of his services in the discover...  
    21  in recognition of the fresh originality and tr...  
    22  in recognition of the numerous and brilliant c...  
    23  for its striving in public law to develop peac...  
    24  for his investigations of the densities of the...  
    25  in recognition of his work on the physiology o...  
    26  in recognition of his services in the advancem...  
    27  because of his outstanding merits as an epic w...  
    28      for her audacity to oppose the horrors of war  
    29                       for his work on cathode rays  
    30  for his investigations and discoveries in rela...  
    


```python

```
