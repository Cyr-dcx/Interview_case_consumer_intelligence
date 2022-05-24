# interview_case_consumer_intelligence
Consumer segmentation

Process summary : 
  
 1) Exploratory Data Analysis on products, clients and transactions_light
 2) From transactions_light, construction of the X dataframe which will be used for modelling
 3) Modelling and results interpretation

1 - Exploratory Data Analysis on products, clients and transactions_light :  
After exploring the data, demographic data was discarded to focus on purchasing behavior.  
Indeed the age data was too incomplete to be usable and the client_type category had an over-representation of the male category.

2 - Features computed :
   
> <span style="font-family:Verdana"> `client_id` : client id  
`n_transactions` : total transactions per client  
`total_amount_per_client` : total amount per client  
`mean_amount_per_transac` : average amount per ticket per client  
`total_product_per_client` : number of products per client  
`mean_product_per_transac` : average number of products per ticket per client  
`unique_product_per_ticket` : number of unique product per ticket per client  
`product_cat` : number of categories the cliend has purchased in  </span>

> <span style="font-family:Verdana"> `n_store` : number of store where the client made a purchase  
`client_type` : male, female, company  
`zipcode` : first two digits of a zipcode  
`client_presence` : number of month since the client's account creation date  
`frequency_orders`: ratio of number of month with a transactions divided by presence of a client account  
`n_month_transac` : number of months with a purchase made by the client  
`recency` : number of month since the client last purchase  </span>

> <span style="font-family:Verdana"> For each time of the day (A), it is the number of transactions made by client during this time :  
B = `['apres_midi','matin', 'midi', 'soir']`  </span>

> <span style="font-family:Verdana"> For each product category (B), it is the number of transactions made by client in one category :  
C = `['Autres', 'Carrelage', 'Chauffage', 'Cuisine',  
     'Dressing', 'Droguerie', 'Décoration', 'Electricité et domotique',  
     'Jardin', 'Luminaires', 'Matériaux de construction', 'Menuiserie',  
     'Outils', 'Peinture', 'Plomberie', 'Quincaillerie', 'Robinetterie',  
     'Salle de bains', 'Terrasse']` </span>

3 - Modelling & Result :  
I choose to run 2 Kmeans models with different features first RFM (recency, frequency, monetary) features and then a focus on time features (time of the day and day of the week). 
In order to keep a better interpretability, I prefered not to use a PCA method
To evaluate the models, I use a silhouette metric. 
I also check the % of my client into each cluster.

