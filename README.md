# Data Analysis

## Project Inbound Marketing
The launch of a new innovative product that will help the population to access banking services through smartphones is coming. The goal is to convert 1,000 customers in the most unbanked cities in Brazil.

Actions to identify the cities for the campaign:

1) Classify Brazilian cities by the level of banking.
2) Estimate the number of customers converted in each city.

The final database should contain:

- Name of the city
- State
- Population
- Level of banking
- Converted Customers

## Inbound Marketing Analysis Roadmap

Databases used:

- STATIONS: Database of the number of service stations.
- PAE: Database of the number of electronic service stations.
- AGENCIES: Database of the number of branches.
- pop: Database of population by municipality.
- freq_municipio: Database of the sum of Number of branches + Number of Service Points + Number of Electronic Service Points by municipality.
- plano_bancarizacao: Database with bankarisation level, IDHM and number of postpaid per municipality.
- IDHM: Database with the IDHM of each municipality.
- final delivery: final database with the name of the city, state, population, banking level and converted customers.

1°) I created a file in R called join_table, where I joined the POSTOS, PAE, AGENCIES databases grouped by municipality to have in a single table the sum of the number of branches + number of service points + number of electronic service points.

2°) I created another file in R called bank_level, where I joined the freq_municipio, pop and IDHM databases grouped by municipality. Before doing the grouping I had to put all the municipalities in capital letters and without accents, because as the bases came from different places I had to standardize everything. After grouping I created a new variable called bankarization level and then a table with the variables: municipality, state, population, bankarization and IDHM. Finally I selected the 1000 most unbanked cities and ordered them in ascending order.

3°) The last file in R called prob_inbound uses the table bank_level which contains all the necessary variables to know the probability of conversion. After I created the state teledensity variables for postpaid cell phones, municipal population adjustment coefficient and conversion probability (in percentage). Finally, I created the variable of interest, which is the number of converted customers, creating a table with: municipality, state, population, banking level and converted customers. The Excel table called entrega.final is the one that contains the list with the minimum number of cities necessary to achieve the objective with the information for each city.

## Project Customer Segmentation
The objective of the team is to build a predictive model that will produce the highest profit for the next direct marketing campaign, scheduled for the next month. The new campaign, sixth, aims at selling a new gadget to the Customer Database. To build the model, a pilot campaign involving 2.240 customers was carried out. The customers were selected at random and contacted by phone regarding the acquisition of the gadget. During the following months, customers who bought the offer were properly labeled. The total cost of the sample campaign was 6.720MU and the revenue generated by the customers who accepted the offer was 3.674MU. Globally the campaign had a profit of 3.046MU. The success rate of the campaign was 15%. The objective is of the team is to develop a model that predicts customer behavior and to apply it to the rest of the customer base. Hopefully, the model will allow the company to cherry pick the customers that are most likely to purchase the offer while leaving out the non respondents, making t he next campaign highly profitable. Moreover, other than maximizing the profit of the campaign, the CMO is interested in understanding to study the characteristic features of those customers who are willing to buy the gadget.

The data set contains sociodemographic and firmographic features about 2.240 customers who were contacted. Additionally, it contains a flag for those customers who responded the campaign, by buying the product.

In this project, the RFM calculation is made in order to understand how customers should be classified.
Afterwards a predictive classification model is made using the Naive Bayes algorithm.

Customer Segmentation: https://datastudio.google.com/s/qboeT6fS9rE
