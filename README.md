# Medicine_Analytics
## Overview
In this project, I am undertaking an in-depth exploration of medical data sourced from Bangladesh. The data, acquired through web scraping utilizing the **Scrappy** framework, originates from [medex.com.bd](https://medex.com.bd/). To seamlessly integrate this data into a structured framework, I have employed the **Django REST** Framework. The information is systematically stored within a **PostgreSQL** database, maintaining relational integrity between various models.
### Data Source
[Assorted Medicine Data Bangladesh](https://www.kaggle.com/datasets/ahmedshahriarsakib/assorted-medicine-dataset-of-bangladesh)

### Customizations 
- Auto complete relational files
- Custom filtering (Alphabetical , Model Property)
- Bulk Actions (export csv)
- Developed a bespoke Scrapy command that enables the execution of Scrapy spiders directly from the Django command line.
   - ```python
     python manage.py <spider_name>
     ```
- Tailored Django commands designed for specific functionalities within the Django framework.
   - To export models to CSV
      ```python
     python manage.py <export_model_name> <export_data_path>
      python manage.py export_medicine_data /home/ahmed/Desktop/medicine_data.csv
     ```
  - To export generic monograph PDFs
    ```python
    python manage.py export_generics_monograph
    ```
I incorporated proxy configuration settings into the Scrapy framework.

## Run
- Establish a Python virtual environment and execute the provided commands from the root directory-
```python
- pip install -r requirements.txt
```
- Executing this command will launch the Django application-
```python
python manage.py runserver
```
- Perform migrations prior to running the application-
```python
python manage.py makemigrations && python manage.py migrate
```
- To Execute all spiders to intiate the crawling process-
```python
python run_crawler.py
```
- To Launch a designated spider individually-
```python
python manage.py <spider_name>
```
ex - ```python python manage.py med ```

## Data Analytics 
### Dataset
The dataset obtained through web scraping is accessible on Kaggle under the title 
[Assorted Medicine Dataset of Bangladesh](https://www.kaggle.com/datasets/ahmedshahriarsakib/assorted-medicine-dataset-of-bangladesh)

The dataset comprises 6 CSV files, each accompanied by a list of their respective columns and features.
1. Medicine.csv (21k+ entries)
   - Brand name
   - Medicine type(allopathic or herbal)
   - Generic
   - Strength
   - Manufacturer
   - Package container(package info)
   - Package size(unit price)
2. Manufacturer.csv (245 entries)
   - Name
3. Indication.csv (2k+ entries)
   - Name
4. Generic.csv (~1700-1800 entries)
   - Name
   - Monographic link (PDF URL)
   - Drug class
   - Indication
   - Generic details such as "Indication description", "Pharmacology description", "Dosage & Administration description" etc.
5. Drug class.csv (~400 entries)
   - Name
6. Dosage form.csv (~120 entries)
   - Name

## Test
Workflow Script- [django-ci.yml]
Run the tests using:
```python
coverage run --omit='*/venv/*' manage.py test
```
or 
```python
python manage.py test
```
Check the coverage
```python
coverage html
```

## Build With

```python
Django==3.2.12
djangorestframework==3.12.2
django-admin-autocomplete-filter==0.7.1
django-filter==21.1
coverage==6.2
Scrapy==2.4.1
scrapy-djangoitem==1.1.1
psycopg2==2.9.3
```
## Preview 

![pic 1](https://github.com/NAGARJX/Medicine_Analytics/assets/151472079/0214ec45-6209-45e2-a1fb-78909e10e21c)

![pic 2](https://github.com/NAGARJX/Medicine_Analytics/assets/151472079/6d6b8697-293e-49a4-9fb5-fde8abccf009)

![pic 3](https://github.com/NAGARJX/Medicine_Analytics/assets/151472079/2450c49a-dcad-4125-869a-abd370c15668)

![pic 4](https://github.com/NAGARJX/Medicine_Analytics/assets/151472079/cdc28bda-faf4-4cb5-ad4f-545b7649c57d)




