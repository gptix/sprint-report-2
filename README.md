# Labs-Sprint-Challenge-2.1- Follow design pattern and architectural guidelines
This challenge allows you to practice the concepts and techniques learned over the past week and apply them by providing answers to questions related to following architectural and design decisions of your Labs product.

In your challenge this week, you will demonstrate understanding over these topics by responding to 2 prompts

## Instructions
Read these instructions carefully

Understand exactly what is expected before starting this Journal Entry.

You are not allowed to collaborate during the Journal Entry.

However, you are encouraged to follow the twenty-minute rule and seek support from your TL if you need direction.

Your work reflects your proficiency in user interface and your command of the concepts and techniques in team planning and product vision.

We have allocated time on your schedule to ensure that you get this done at the end of each sprint.

**For Full Time Students: Please submit your work on this journal entry before 12pm PST every Friday.**

# Prompt 1
For this response, please focus on your individual contributions.

**Engineers:**

## Describe your contribution to your team's goals this sprint.

How did you ensure that you implemented the designer's vision accurately?

The DS team (including me)

- discussed the reporting requirements for RC1 and RC2. We then
- tested
- locally, and then
- on a Heroku instance.
- used pair (team) programming to improve our code.
- We then
  - tested communication between the backend and the DS layer, including
    - URL's,
    - method types,
    - authorization, and
    - payload content.

## What were the biggest challenges you faced this sprint?
The biggest (and it was **not very big, at all**) was communication between me and the BE team regarding the authorization token. **This was easily handled.**

## Description of the data layer of your application. (Limited to Data Science Layer)
The organization of the DS portion of the model (for this RC) is:

- A request contains a JSON document that contains a key-value pair with the key "id" and an integer-like string (and some other pairs, which are not yet used)
- Our response contains a JSON document that contains a key-value pair with the key "optimal time" and a string like "1PM"
- This response is sent via a request that has as a URL a base URL concatendated with the "id" value mentioned above.

## Describe your product's application structure and code patterns. Why or why not is your team using a linter? If applicable, describe the structure of your API.

### Application Structure:
#### Front-end
React web interface that presents information to a user, receives data input, receives control actions, calls the back end, receives response from the back end, and presents results to the user.

#### Back-end
A Javascript server that communicates with the front-end as appropriate, maintains a Postgres database, and makes requests to, and receives responses from, a "DS layer". The Postgres database is used to maintain information about users and user transactions.

#### Data Science layer
A Python server (a Flask instance) that communicates with the backend via HTTP requests, authenticates, and constructs appropriate responses.

### Linter?
Team members did individually use linters. This could be enforced more thoroughly going forward.

### Code Patterns (DS):
- standard and common libraries
- use of decorator pattern to abstract out authentication
- use of JSON and requests libraries to construct and execute HTTP requests
- We made progress in shrinking code by using patterns like inline calls to avoid instantiation of unneeded variables, and application of list comprehensions.

### API 
#### Request from Backend to DS layer
- POST method
- endpoint URL: /recommend
- authorization using a request header containing a key value pair containing a token as a value
body/payload/data is a JSON document containing, at least, a key-value pair contining a pair like "id" : "17"
- request (in response to earlier request) from DS layer to Backend

#### Response to Backend layer
- PUT method
- endpoint URL: (as specified by BE team, including the value for the "id" as received in a request
- authorization using a request header containing a key value pair containing a token as a value
- body/payload/data is a JSON document containing, at least, a key-value pair contining a pair like "Optimal Time" : "1PM"

#### request/response to Twitter
- Request via Tweepy API

**Data scientists:**
Working with the engineering and design teams

- We worked with design and front end teams by participating in demonstrations and discussions, without, and with, stakeholder.
 - We worked with the backend team by conducting videoconferences, examining code, running tests, and communicting via Slack

### How did design/engineering help guide the solution to the product's data science problems?

Design helped by confirming that the user's experience would be to log in (setting an ID) and submitting proposed tweets for recommendtion of time to send.

Backend helped by providing nitty gritty detail about authentication and payload structure, and discussing (although this is not a direct DS-layer concern) how data would be stored in a Postgres database.

## Prompt 2 - To be completed if your team deviated from your plan
Now that you've been through or are nearly completing a full product release cycle, we'd like to know how your plan changed.

**The DS team's work did not deviate substantially from plan, with regard to RC 1.**

We continue to examine ways to make RC 2 great.

## My work and contributions to the team to deliver per spec
- Worked with backend team to get authentication working
- participated in team coding with DS team
- tested locally, then on Heroku instances with the DS team, and then with the backend team
- examined and recommended regarding the API between the backend and DS layer

## Contribution to the overall delivery of the stakeholder/design requirements
- Helped make the decision to deliver, in RC 1, a benchmark response, per a study by Buffer
- Ensured that backend-data science interactions were per spec (and would be improveable in lter RC's)

## Details on working cross-functionally
- Described above, and
- direct, detailed work with the bckend team on designing and testing API calls and authentication
- project-team-level discussions on user interaction, stakeholder interests

### Give and take
The Data science team explained:

- limitations of the Tweepy API (size of text, frequency of calls, size of response)
- limitations of the Twitter API (difficulty in getting "whed did engagement occur", which is different to "did engagement occur if I sent at time X") 
- We came to a good working agreement with the Backend team on the way to implement authentication, how to get tokens, and how longer DS work cycles might lead to need for asynchronous handling in future.

## Processes followed during the development/design cycle:
- Read description of project
- Meet with stakeholder to hear firsthand, and ask clarification and scoping questions
- DS team considers design (type of server, overall function goals)
- DS validates usefulness of design with BE team
- Decide within DS team who works on what
- Communicate and meet withing DS team to track work, test, tighten
- Agree with BE team on API (authentication, request methods, endpoints, payload contents) AND DATA FLOW
- Communicate and meet with BE team to track work, test, tighten

Please fill out if, during this release canvas, you deviated from your original plan

**Not applicable.**

## Submitting your work
To do momentarily.