# Top Skills Required for an Entry Level Data Analyst

## Background
I always curious about what are the top skills required by potential employers for an entry-level job. Blog posts and articles online are often broad and do not provide actual data on how many potential employers ask for a set of specific skills. 

## Project Tasks
- __Part 1__ is to gather a small data sample from a job posting site(we will focus on Linkedin). 
- __Part 2__ is to filter each job description and categorize a list of asked skills for the final analysis. Skills will be rank based on how often they appear on a job posting. 

## Scope
- __Location:__ Since I am based out of SF Bay Area, I would like to target the jobs specified to the region in my search query. 
- __Job Level:__ The main demographic of this project is for an audience of new college graduates and people who are just getting started in data analytic. Therefore, anything above entry-level and associate will be excluded from the data scrape. 
- __Skills Focus:__ Project will not touch on salary or any other metrics. A list of predefined skills used in this project is widely accepted as the industry standard.
- __Sample Size:__ Since most job posting sites have a limit on how many posting will be displayed, the aim is to gather as much as possible without triggering the "I am not a robot" feature. 

## Tool
- Python in Jupyter Notebook
    - For the web scrapping process and data analysis. 

## Content

### Scrapping with Selenium
Selenium was chosen due to its various kits and testing features. It came in quite handy when dealing with reloading and initiating the "Show More" button on the Linkedin site. 

The dataset contains 300+ postings in 2 separates .csv files: _jobs_ and _jobs_desc_. This separation was mainly done due to personal preference. The target observations are the job's 
- id
- title
- company name
- location
- description. 

Filters for entry-level and location restriction are applied in the search query url. Once job completed, the data will be processed into .csv files: _filtered_job_ and _filtered_job_desc_. This will make processing in part 2 a bit easier.  

### Job Desc Analysis with NLP Module
Using the NLP module, each job description was filtered and categorized if matches skills in a predefined list. Skills are categorized by the cumulative sum of how many times they appeared on all the scraped job postings. After much time searching on the web, the list below included all the most common skills found:
- `tool_skill = ['server',
              'cloud',
              'sql',
              'mysql',
              'python',
              'r',
              'tableau',
              'power bi',
              'looker',
              'powerpoint',
              'sheet',
              'gsuite',
              'jupyter',
              'javascript',
              'java',
              'excel',
              'statistic',
              'model',
              'word',
              'bi']`

To summarize, each job description is tokenized and matched against the defined skills list. If a skill is found, it will be added into a separated list to be tally up. Below is the result for the top asked skill from the dataset. 

![chart](https://github.com/mbo0000/Portfolio/blob/main/DataAnalyticTopSkills/charts/top_tools?raw=true)

SQL appears on ~56% of the total 300+ job posts with Excel and Tableau in the high 40s% and mid 30s%.

### Conclusion
No surprises here in Silicon Valley. The top skills are SQL, Excel(or spreadsheet), and Tableau respectively. The 4th place is Python. 

For newly college graduates and beginners, these should be the top skills to focus on when applying for any entry-level data analyst job.

## NOTE:
Data scraped from Linkedin was performed in early October - 2021. The scraping process may no longer be applicable with the platform updates. 
