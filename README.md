[<img src="https://run.pstmn.io/button.svg" alt="Run In Postman" style="width: 128px; height: 32px;">](https://app.getpostman.com/run-collection/51837689-71cfde2a-d4d1-46f4-aa99-34b095e66a96?action=collection%2Ffork&source=rip_markdown&collection-url=entityId%3D51837689-71cfde2a-d4d1-46f4-aa99-34b095e66a96%26entityType%3Dcollection%26workspaceId%3D82b6bd25-0a0a-4d13-ada7-9a0e41846b3a#?env%5Blin%20-%20hw3%5D=W3sia2V5IjoicmFuZG9tVXNlciIsInZhbHVlIjoidXNlcl80NTMwOSIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJhbnkiLCJzZXNzaW9uVmFsdWUiOiJ1c2VyXzI5NTMzIiwiY29tcGxldGVTZXNzaW9uVmFsdWUiOiJ1c2VyXzI5NTMzIiwic2Vzc2lvbkluZGV4IjowfSx7ImtleSI6Imp3dFRva2VuIiwidmFsdWUiOiJKV1QgZXlKaGJHY2lPaUpJVXpJMU5pSXNJblI1Y0NJNklrcFhWQ0o5LmV5SnBaQ0k2SWpZNVlqa3hZemt6TjJZMk5qazVNbVZoTkdWbE16RmhNeUlzSW5WelpYSnVZVzFsSWpvaWRYTmxjbDgwTlRNd09TSXNJbWxoZENJNk1UYzNNemN6T1RFMU5pd2laWGh3SWpveE56Y3pOelF5TnpVMmZRLnZua05nbUppbWJMdG14dm4tQkJpZkp0SE9SV3BGQU5vcjFTUzNZd2Rsb0kiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoiYW55Iiwic2Vzc2lvblZhbHVlIjoiSldULi4uIiwiY29tcGxldGVTZXNzaW9uVmFsdWUiOiJKV1QgZXlKaGJHY2lPaUpJVXpJMU5pSXNJblI1Y0NJNklrcFhWQ0o5LmV5SnBaQ0k2SWpZNVlqa3haREU0TjJZMk5qazVNbVZoTkdWbE16RmpNU0lzSW5WelpYSnVZVzFsSWpvaWRYTmxjbDh5T1RVek15SXNJbWxoZENJNk1UYzNNemN6T1RJNE9Td2laWGh3SWpveE56Y3pOelF5T0RnNWZRLmdYNml1R3l4dGNoUUJ4eVg5RDNpd2VwRkM1VnAydEN6eWlDQkJETkN0dk0iLCJzZXNzaW9uSW5kZXgiOjF9LHsia2V5IjoibW92aWVJZCIsInZhbHVlIjoiNjliOTFjOTQ3ZjY2OTkyZWE0ZWUzMWE3IiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6ImFueSIsInNlc3Npb25WYWx1ZSI6IjY5YjkxZDE5N2Y2Njk5MmVhNGVlMzFjNSIsImNvbXBsZXRlU2Vzc2lvblZhbHVlIjoiNjliOTFkMTk3ZjY2OTkyZWE0ZWUzMWM1Iiwic2Vzc2lvbkluZGV4IjoyfV0=)

# Assignment Three
## Purpose
The purpose of this assignment is to get comfortable working with a NoSQL database (MongoDB). 

For this assignment you will create a Users collection to store users for your signup and signin methods.  You will pass Username, Name and Password as part of signup.  To get a token you will call SingIn with username and password only.  The token should include the Name and UserName (not password)

You will also create Movies collection to store information about movies.  All endpoints will be protected with the JWT token received by a signin call. 

## Requirements
Create a collection in MongoDB to hold information about movies
- Each entry should contain the following
    - title (string, required, index)
    - releaseDate
    - genre (Action, Adventure, Comedy, Drama, Fantasy, Horror, Mystery, Thriller, Western, Science Fiction)
    - Array of three actors that were in the film
        - actorName
        - characterName
    - The movie collection should have at least five movies
- Create a NodeJS Web API to interact with your database
    - Follow best practices (e.g. /movies collection)
    - Your API should support all CRUD operations (through HTTP POST, PUT, DELETE, GET)
    - Ensure incoming entities contain the necessary information.  For example if the movie does not contain actors, the entity should not be created and an error should be returned 
- All endpoints should be protected with a JWT token (implement signup, and signin)
    - For this assignment you must implement a User database in Mongo
        - name
        - username 
        - password (should be hashed)
    - If username exists the endpoint should return an error that the user already exists
    - JWT secret needs to be stored in an environment variable
- Update the Pre-React CSC3916_REACT placeholder project to support /signup and /signin methods.  The React Single Page App should use your Assignment 3 API to support those two operations.

## Submissions
- All source code should be stored on github (remember .gitignore for node_modules)
- API needs to be deployed to heroku or render
- React Website that allows user to signup and singin (we did this in class)
- PostMan test collection that 
    - Signs Up a user (create a random user name and random password in your pre-test)
    - SignIn a User – parse token and store in postman environment variable
    - A separate call for each endpoint (save a movie, update a movie, delete a movie and get a movie)
    - Test error conditions (user already exists)
        - SignUp (user already exist)
        - Save Movie (missing information like actors (must be at least three), title, year or Genre)

- Create a readme.md at the root of your github repository with the embedded (markdown) to your test collection
    - Within the collection click the (…), share collection -> Embed
    - Static Button
    - Click update link
    - Include your environment settings
    - Copy to clipboard 
- Submit the Url to canvas with the REPO CSC_3916
- Note: All tests should be testing against your Heroku or Render endpoint

| Route | GET | POST | PUT | DELETE |
| --- | --- | --- | --- | --- |
| movies | Return all movies| save a single movie | FAIL | FAIL |
| movies/:movieparameter | Return a specific movie based on the :movieparameter | FAIL | Update the specific movie based on the :movieparameter in your case it’s the title | Delete the specific movie based on the :movieparamters your case it’s the title |*

* If Query String (Later Homework) reviews=true aggregate in reviews |

## Rubic
- -5 for missing REACT site (-2 if you are not able to signup or signin on the react site) that is all we implemented
- -1 for MovieSchema missing any of the attributes (array of actors, genre, year released or title)
- -2 for missing routes for /movies (POST/PUT/DELETE/GET)
- -1 for missing authentication on routes
- -2 for not deployed on Heroku/Render
- -1 missing Test error conditions
- -1 missing PostMan tests (signup, signin, separate call for each route)

## Resources
- https://www.mongodb.com/cloud/atlas
- Create a Free Subscription *Amazon
- https://render.com/docs/deploy-create-react-app **important: Environment Variable for https://github.com/AliceNN-ucdenver/CSC3916_REACT env.REACT_APP_API_URL, this weekend I will look at changes (I believe only 1 change in the actions)
