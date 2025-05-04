# ETL-Logistic-Regression
# HR Analytics: Job Change of Data Scientists
## Intorduction
Context and Content

A company which is active in Big Data and Data Science wants to hire data scientists among people who successfully pass some courses which conduct by the company.

Many people signup for their training. Company wants to know which of these candidates are really wants to work for the company after training or looking for a new employment because it helps to reduce the cost and time as well as the quality of training or planning the courses and categorization of candidates.

Information related to demographics, education, experience are in hands from candidates signup and enrollment.

**import pandas as pd**

## Data Sources
1. Enrollies' data
- Import data vào:
ggsheet_url = "https://docs.google.com/spreadsheets/d/1VCkHwBjJGRJ21asd9pxW4_0z2PWuKhbLR3gUHm-p4GI" + "/export?format.xlsx"
enrollies_data = pd.read_excel(ggsheet_url)


- Check thông tin data
enrollies_data.info()

![image.png](data:image/png;base64,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)

Kết quả: data đang có nhiều dòng bị NULL ở cột gender, cần fill data vào những dòng đó.


- Fill data:
enrollies_data["gender"] = enrollies_data["gender"].fillna("unknow")
enrollies_data = enrollies_data.convert_dtypes()

- Check các unique của cột City:
enrollies_data["city"].unique()

## 2. Enrollies' education
After enrollment everyone should fill the form about their education level. This form is being digitalized manually. Educational department stores it in the Excel format here: https://assets.swisscoding.edu.vn/company_course/enrollies_education.xlsx

- Import data
enrollies_education = pd.read_excel("enrollies_education (1).xlsx")

- Check thông tin data
enrollies_education.info()

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 19158 entries, 0 to 19157
Data columns (total 4 columns):
 #   Column               Non-Null Count  Dtype 
---  ------               --------------  ----- 
 0   enrollee_id          19158 non-null  int64 
 1   enrolled_university  18772 non-null  object
 2   education_level      18698 non-null  object
 3   major_discipline     16345 non-null  object
dtypes: int64(1), object(3)
memory usage: 598.8+ KB

Kết quả: Có nhiều cột bị NULL, cần clear sạch dữ liệu. Nhưng quá nhiều dòng bị NULL, nên fill unknown

enrollies_education["enrolled_university"] = enrollies_education["enrolled_university"].fillna("unknown")
enrollies_education["education_level"] = enrollies_education["education_level"].fillna("unknown")
enrollies_education["major_discipline"] = enrollies_education["major_discipline"].fillna("unknown")

- Convert thành đúng định dạng
enrollies_education = enrollies_education.convert_dtypes()

- Check lại thông tin lần nữa
enrollies_education.info()

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 19158 entries, 0 to 19157
Data columns (total 4 columns):
 #   Column               Non-Null Count  Dtype 
---  ------               --------------  ----- 
 0   enrollee_id          19158 non-null  Int64 
 1   enrolled_university  19158 non-null  string
 2   education_level      19158 non-null  string
 3   major_discipline     19158 non-null  string
dtypes: Int64(1), string(3)
memory usage: 617.5 KB

## 3. Enrollies' working experience
Another survey that is being collected manually by educational department is about working experience.

Educational department stores it in the CSV format here: https://assets.swisscoding.edu.vn/company_course/work_experience.csv

- Import data
enrollies_experience = pd.read_csv("https://assets.swisscoding.edu.vn/company_course/work_experience.csv")

- Check thông tin data
enrollies_experience.info()

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 19158 entries, 0 to 19157
Data columns (total 6 columns):
 #   Column               Non-Null Count  Dtype 
---  ------               --------------  ----- 
 0   enrollee_id          19158 non-null  int64 
 1   relevent_experience  19158 non-null  object
 2   experience           19093 non-null  object
 3   company_size         13220 non-null  object
 4   company_type         13018 non-null  object
 5   last_new_job         18735 non-null  object
dtypes: int64(1), object(5)
memory usage: 898.2+ KB

- Kiểm tra data 
enrollies_experience.head()

|index|enrollee\_id|relevent\_experience|experience|company\_size|company\_type|last\_new\_job|
|---|---|---|---|---|---|---|
|0|8949|Has relevent experience|\>20|NaN|NaN|1|
|1|29725|No relevent experience|15|50-99|Pvt Ltd|\>4|
|2|11561|No relevent experience|5|NaN|NaN|never|
|3|33241|No relevent experience|\<1|NaN|Pvt Ltd|never|
|4|666|Has relevent experience|\>20|50-99|Funded Startup|4|

- Fill data
enrollies_experience["experience"] = enrollies_experience["experience"].fillna("mode")
enrollies_experience["company_size"] = enrollies_experience["company_size"].fillna("unknown")
enrollies_experience["company_type"] = enrollies_experience["company_type"].fillna("Other")
enrollies_experience["last_new_job"] = enrollies_experience["last_new_job"].fillna("unknown")

- Check data
enrollies_experience.info()

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 19158 entries, 0 to 19157
Data columns (total 6 columns):
 #   Column               Non-Null Count  Dtype 
---  ------               --------------  ----- 
 0   enrollee_id          19158 non-null  Int64 
 1   relevent_experience  19158 non-null  string
 2   experience           19158 non-null  string
 3   company_size         19158 non-null  string
 4   company_type         19158 non-null  string
 5   last_new_job         19158 non-null  string
dtypes: Int64(1), string(5)
memory usage: 916.9 KB

- Định dạng dạng lại format
enrollies_experience = enrollies_experience.convert_dtypes()

## 4. Training hours
From LMS system's database you can retrieve a number of training hours for each student that they have completed.

Database credentials:

Database type: MySQL

Host: 112.213.86.31

Port: 3360

Login: etl_practice

Password: 550814

Database name: company_course

Table name: training_hours

- Import thư viện
!pip install pymysql
!pip install sqlalchemy

- Import data
from sqlalchemy import create_engine
import pymysql
user_name = "etl_practice"
pw = "550814"
server = "112.213.86.31"
port = "3360"
db_name = "company_course"
engine = create_engine('mysql+pymysql://{0}:{1}@{2}:{3}/{4}'.format(user_name,pw,server,port,db_name))
training_hours = pd.read_sql_table('training_hours', con=engine)

- Check thông tin data
training_hours.info()

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 19158 entries, 0 to 19157
Data columns (total 2 columns):
 #   Column          Non-Null Count  Dtype
---  ------          --------------  -----
 0   enrollee_id     19158 non-null  int64
 1   training_hours  19158 non-null  int64
dtypes: int64(2)
memory usage: 299.5 KB

- Check data 5 dòng đầu
training_hours.head()

|index|enrollee\_id|training\_hours|
|---|---|---|
|0|8949|36|
|1|29725|47|
|2|11561|83|
|3|33241|52|
|4|666|8|

## 5. City development index
Another source that can be usefull is the table of City development index.

The City Development Index (CDI) is a measure designed to capture the level of development in cities. It may be significant for the resulting prediction of student's employment motivation.

It is stored here: https://sca-programming-school.github.io/city_development_index/index.html

- Import data
list_table = pd.read_html("https://sca-programming-school.github.io/city_development_index/index.html")
first_table = list_table[0]

- Check 5 dòng đầu
first_table.head()

|index|City|City Development Index|
|---|---|---|
|0|city\_103|0\.92|
|1|city\_40|0\.7759999999999999|
|2|city\_21|0\.624|
|3|city\_115|0\.789|
|4|city\_162|0\.767|

## 6. Employment
From LMS database you can also retrieve the fact of employment. If student is marked as employed, it means that this student started to work in our company after finishing the course.

Database credentials:

Database type: MySQL

Host: 112.213.86.31

Port: 3360

Login: etl_practice

Password: 550814

Database name: company_course

Table name: employment

- Import data
user_name = "etl_practice"
pw = "550814"
server = "112.213.86.31"
port = "3360"
db_name = "company_course"
engine = create_engine('mysql+pymysql://{0}:{1}@{2}:{3}/{4}'.format(user_name,pw,server,port,db_name))
employment = pd.read_sql_table('employment', con=engine)

- Check thông tin
employment.info()

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 19158 entries, 0 to 19157
Data columns (total 2 columns):
 #   Column       Non-Null Count  Dtype  
---  ------       --------------  -----  
 0   enrollee_id  19158 non-null  int64  
 1   employed     19158 non-null  float64
dtypes: float64(1), int64(1)
memory usage: 299.5 KB

- Check 5 dòng đầu
employment.head()

|index|enrollee\_id|employed|
|---|---|---|
|0|1|0\.0|
|1|2|1\.0|
|2|4|0\.0|
|3|5|0\.0|
|4|7|0\.0|
