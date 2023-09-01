# Data Flow Documentation
``` @TODO: Describe how Data flows end to end. Attach a diagram if possible. Note any differences between dev and prod. ```
``` Please indicate the name of the component handling the data at critical steps of the data flow.``` <br>
``` Eg. Writing out the name of DAGs, Dataset/Tables, Apps.``` <br>
``` Note: Include relevent information such as scheduling or how the project works in production.```

## Input and Output Data
``` @TODO: List down input and output data. Write down where data comes from and where it goes to. ```
### Input A
- Description: Scraped data from the website (article text, date, author)
- File Location: Internet
### Output A
- Description: Ingested to ES for the WebApp.
- File Location: Elasticsearch DB (dev-elasticsearch VM)