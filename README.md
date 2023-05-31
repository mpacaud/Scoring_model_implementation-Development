## Scoring model implementation - Backend

**Credit Scoring** is a risk analysis tool for granting credit. Based on statistical methods, it takes into account a lot of information relating to the loan applicant to assess the risk of non-repayment. In concrete terms, the tool assigns a score to a loan application by statistical analysis on a reference basis (expired files whose outcome is known).

Although very widespread in credit organizations, many aspects remain to be improved. Mainly:

**- trust**

The tool's impartiality is often cited as a virtue by the industry but does not necessarily convince applicants, especially when their credit application is refused.

**- transparency of information**

The new European regulation on the protection of personal data entered into force on May 25, 2018 (https://www.cnil.fr/fr/reglement-europeen-protection-donnees). Article 12 specifically deals with "Transparency of information and communications and modalities for exercising the rights of the data subject".

**- performances**

Regardless of the method used to establish credit application scores, the results can be misleading. This may be the case for "non-standard" files, for example, which encounter few similar cases in the processing sample.

>The quality of the reference data is therefore very important. The aim is to have a database that is as representative as possible of the situations to be dealt with.

The techniques and methods used to build the model obviously have a significant impact on its performance. No model is perfect and there will always be instances of poor predictions.

>The technical challenge is to minimize these cases.


## Project

This project aims to create a **Credit Scoring** tool based on **Machine Learning** technologies. Machine Learning has the reputation of being not very transparent and of approaching a black box. This does not favor its acceptance with regard to the first two points mentioned above.

>Nevertheless, enormous progress has been made to date and the field of Machine Learning offers very interesting solutions to improve the understanding of decision-making processes.


**Modelization**

The objective is twofold:

+ The model must allow to define the ***probability of default of a repayment*** of a credit on the basis of information relating to the customer.
+ It must also offer a certain level of transparency concerning the data and their processing in order to implement methods of ***interpretability*** of the variables.

>The tool was modeled using **supervised learning** technologies.

The main modeling steps are described in the methodological note:


**Application**

Beyond the technical aspects, the transparency of the tool is also characterized by the possibilities of interaction with it in order to carry out additional analyzes on the basis of the results proposed.

+ For example, you want to be able to compare 2 similar files whose credit granting predictions are different and visualize the variables that influenced the decisions.
+ You may also want to perform simulations to estimate the degree to which a file has been refused and identify the discriminating criteria.

>The model was deployed via a web application based on **Streamlit** and **Flask**.


## Plan

The project was split into two parts:

### Part 1: Development

The first part of the project consists of realizing:
- an exploratory data analysis.
- their processing in order to build the dataframes adapted to the modeling of a Machine Learning tool.
- the modeling of a supervised learning system.
- the interpretation of the importance of features at local and global level.
- simulation of data drift to determine a maintenance period in order to maintain optimal prediction performance.
- the development of the web application which is divided into 2 sub-parts: one frontend based on streamlit (stored on GitHub: https://github.com/mpacaud/Scoring_model_implementation-Frontend.git) and the other backend based on Flask (stored on GitHub: https://github.com/mpacaud/Scoring_model_implementation-Backend.git).

### Part 2: Deployment

**Local**

To launch the application locally, just run:
- first the test server provided with Flask.
- then, the streamlit server which communicates to the previous server the requests sent by the user.

**On line**

The deployment of the script is carried out via the Heroku platform. The application dashboard can be loaded with the following link: https://git.heroku.com/mysterious-refuge-87297.git

NB1: By clicking on this link, it is possible to log into the backend server: https://git.heroku.com/hidden-savannah-70356.git
NB2: It seems that the Flask application cannot work on Azure because a package is missing on their linux installation to run the chosen model (LightGBM).

***Warnings***

For reasons of server resource management, it is possible that the application is not permanently maintained on the Heroku hosting site.