# ChatGPT SQL

Connecting ChatGPT to an SQL Server so that you can ask questions about data in natural language, and you also get an answer in natural language.  It works by creating a layer between the user and chatgpt that routes messages between the user and chatGPT on one side, and chatGPT and the SQL server on the other. ChatGPT is indicating whether the message it meant for the user or for the server. What you see in the below image is the following:

1. The user asks a question ("What is the top selling product by revenue in 2013?")
2. The script forwards the question to ChatGPT.
3. ChatGPT responds with a request for schema information.
4. The script queries the database schema in SQL server and sends the result back to ChatGPT.
5. CHatGPT Formulates an SQL query based on the schema information
6. The script executes the query against the database and sends the result back to ChatGPT.
7. ChatGPT interprets the result and formulates an answer (indicating it should be shared with the user)
8. The script shares the answer with the user. ("The top selling product by revenue in 2013 is the Mountain-200 Black, 38.").

THe app is currently configured to work with the [AdventureWorks database](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms), but it should be possible to make it work with any other database as well.

Some caveats:
* The database I use is the AdventureWorks database, which ChatGPT also knows from it's trainingdata, which means its probably performing better than it would with other databases.
* It sometimes breaks, due to ChatGPT not following protocol.

Still I think it's a pretty cool POC :slightly_smiling_face:

![Demo](https://s2.gifyu.com/images/chatgpt-sql-demo.gif)

