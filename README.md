# module10

Name: Zinia Mahabub

JHED ID: zmahabu1

Module Info: Module 10 - Building an Automated CI/CD Pipeline, Due Date: August 4, 2024 at 11:59PM EST

Approach:
1. In order to implement the API, I installed the necessary libraries (`json`, `requests`, `flask`) and 
configured the WMATA API key from Module 7. Then, I defined the `get_incidents` function in `wmata_api.py` to accept the `unit_type` parameter, 
call the WMATA Incidents API, convert the response to JSON, and filter the incidents based on the `unit_type`. Then, 
I created a list of dictionaries for each incident with the required fields: `StationCode`, `StationName`, `UnitName`, and `UnitType`. 
It returned the list of dictionaries as a JSON string to the endpoint caller. Then, I ran and exposed the API endpoint using Flask.

2. To run the unit tests, I downloaded `test_wmata_api.py` and filled in the test code for the 4 unit test cases: `test_http_success`: Verified that both `/incidents/escalators` and `/incidents/elevators` endpoints return a 200 response code.
`test_required_fields`: Verified that each incident returned by the endpoints contains the 4 required fields.
`test_escalators`: Ensured that all incidents returned from the `/incidents/escalators` endpoint have a `UnitType` of "ESCALATOR".
`test_elevators`: Ensured that all incidents returned from the `/incidents/elevators` endpoint have a `UnitType` of "ELEVATOR".
Then, I ran the tests manually using `python3 -m unittest` and `python test_wmata_api.py`.

3. CI/CD Pipeline (Optional):
For this, I Created a free GitHub and CircleCI account then I installed Git and GitHub Desktop on my local machine. Then, a new repository named “module10” was created on GitHub to clone the repository and added the necessary files (`wmata_api.py`, `test_wmata_api.py`, `requirements.txt`, `.circleci/config.yml`). Then I committed and pushed the files to the GitHub repository. Then, I connected the GitHub repository to CircleCI and configured the project. I committed a change to trigger a CircleCI build, which built a Docker container, installed dependencies, checked out the code, deployed it into the container, and executed the unit tests.
   
Known Bugs:
- None identified. All tests pass successfully and the API endpoints return the expected results.
