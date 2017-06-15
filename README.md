##1. CURLs##

##1.1. Creates a new issue with custom fields##

`curl -D- -u uname:pass -X POST --data "{\"fields\": {\"project\": { \"id\": \"10430\" },\"summary\": \"This is a test issue\", \"description\": \"Description\",\"issuetype\": { \"id\" : \"1\"}, \"components\" : [{\"id\":\"10731\"}], \"customfield_10711\" : [{\"id\":\"10500\"}] } }" -H "Content-Type: application/json" http://localhost:8880/jira/rest/api/2/issue/`

##1.2. Returns all issues for XXX##

`curl -D- -u uname:pass -X PUT -d "Content-Type: application/json" http://localhost:8880/jira/rest/api/2/search?jql=project="XXX"`

##1.3. Returns all information on an issue XXX-1##

`curl -D- -u uname:pass -X PUT -d "Content-Type: application/json" http://localhost:8880/jira/rest/api/2/issue/XXX-1`

##1.4. Adds a comment to an existing issue##

`curl -D- -u uname:pass -X PUT -d "{\"update\": {\"comment\": [{\"add\": {\"body\": \"Test comment\"}}]}}" -H "Content-Type: application/json" http://localhost:8880/jira/rest/api/2/issue/KEY-12345`

##1.5. Transitions an issue##

`curl -D- -u uname:pass -X PUT -d "{\"transition\": {\"id\": \"721\"}}" -H "Content-Type: application/json" http://localhost:8880/jira/rest/api/2/issue/XXX-1/transitions`

##1.6. Get a list of all users##
##This returns a list of all users with the letter 'a' in them ##

`curl -D- -u uname:pass http://localhost:8880/jira/rest/api/2/user/search?username=a`

##2. GETs##

##2.1. Get all projects##
`/rest/api/2/project`