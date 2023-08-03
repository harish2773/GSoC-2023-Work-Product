# GSoC 2023 Work Product

<h1 align="center">Google Summer of Code 2023 </h1>

<p align="center"><i>A full report on my Google Summer of Code 2023 work with AOSSIE</i></p>
<p align="center"><i>Project: "Social Street Smart" </i>  👨‍💻</p>



<p align="center">
  <img src="https://i.imgur.com/fF5RFGo.png" />
</p>

### GSoC 2023 Report: Social Street Smart


#### Summary

This was the fifth year for Social Street Smart. Building upon the work done in the previous year, this year's GSoC tasks were aimed to integrate the extension with GPT-3 and implement a rating mechanism for websites to improve their experience. 

Here is a quick summary of the work done over this year:

- :construction_worker: A CI / CD Pipeline has been added with
  - :white_check_mark: Unit Tests for all Newly Created APIs 
  - 🚀 Deployment through the GitLab Pipeline
- :sparkles: New Features -
	-  *OpenAI GPT-3 API*.
	-  *Rating mechanism for website*.
- :bento: Addition of a new front-end where ever needed
- :bug: Fixing bugs 
- :rocket: Deployed the Updated Chrome Extension to the Chrome Webstore.

#### [NEW] Integration of GPT-3 

The integration of the OpenAI GPT-3 API provides users with a powerful tool to gain deeper insights into specific news articles they wish to verify. To access this functionality, users are required to input their unique API key in the settings page of the Chrome extension. The API key is securely stored in the local storage of the Chrome browser and serves as the input for generating prompts for the GPT-3 model.

Once the API key is set up, users can generate up to 30 prompts using their authorized API key.The generated responses are displayed to the user, offering valuable insights and analysis regarding the news article in question. 



#### Unit Testing [ For Newly Created Features ]

I have implemented Unit Testing into the project, that makes it much easier to validate that all the APIs are functioning properly. The tests run in GitLab's CI/CD Pipeline. Unittest was used to run the tests for the APIs.



#### Running the APIs locally

##### GPT3 API

This can be run locally in the same way as they were before GSoC 2023. The steps are as follows

```bash
# Go to the directory of the API
cd /server/Context Analysis

# Install all the requirements
pip install -r requirements.txt

# Run the server
flask run
```
#### How to Get OpenAI API Key

To access the OpenAI API and use services like GPT-3, you need to obtain an API key. Here's how you can get one:

1. Open your web browser and visit the [OpenAI website](https://openai.com/).

2. Sign in to your OpenAI account or create a new account if you don't have one.

3. Once logged in, navigate to the API section or developer portal.

4. Look for the option to "Generate API Key" or something similar.

5. Click on the button to generate a new API key.

6. Follow any additional prompts or instructions provided by the OpenAI platform.

7. Your API key should be generated and displayed on the screen.

**Important**: Treat your API key as sensitive information, similar to a password. Do not share it publicly or in unencrypted formats, as it grants access to your OpenAI account and services.


##### Unit Testing the APIs

Unit testing for the APIs was done using `unittest` . 
To run the tests locally

```bash
cd /server/<directory_of_the_API>
pip install -r requirements.txt
python -m unittest test_file.py
```

#### [NEW] Implementation of Rating Mechanism
The rating mechanism allows users to rate the credibility of websites they visit. This data is aggregated to create a credibility score for each website. Users can then be informed about the reliability of the sources they encounter while browsing.

#### API Endpoints (Serverless Deployment on AWS Lambda)

- Report API : (<https://vsvpgs5rl3.execute-api.us-east-2.amazonaws.com/dev/{proxy+}>)
- SSL API :
  	- ANY : <https://q4ri22coa3.execute-api.us-east-1.amazonaws.com/dev/>
  	- POST : <https://q4ri22coa3.execute-api.us-east-1.amazonaws.com/dev/ssl>
  

#### Project Links
- [Download the Extension (Chrome Webstore)](<https://chrome.google.com/webstore/detail/social-street-smart/ddjcjpfkmcgpgpjhlmdenmionhbnpagm?hl=en-GB&authuser=0>)
- [Chrome Extension Repository](https://gitlab.com/aossie/social-street-smart)
- [All API's Repository](https://gitlab.com/aossie/social-street-smart-api)


#### Issues 
- [SSS-Phase 1](https://gitlab.com/aossie/social-street-smart/-/issues/?sort=updated_desc&state=opened&label_name%5B%5D=GSoC%202022%20Coding%20Phase%201&first_page_size=20)
- [SSS -Phase 2](https://gitlab.com/aossie/social-street-smart/-/issues/?sort=updated_desc&state=opened&label_name%5B%5D=GSoC%202022%20Coding%20Phase%202&first_page_size=20)
- [SSS API - Phase 1 ](https://gitlab.com/aossie/social-street-smart-api/-/issues/?sort=updated_desc&state=opened&label_name%5B%5D=GSoC%202022%20Coding%20Phase%201&first_page_size=20)


#### Merge Requests

The following merge requests were made to the project during GSoC 2023.


##### Social Street Smart API Repository
- [!19 Addition of GPT-3 API to the API repository](https://gitlab.com/aossie/social-street-smart-api/-/merge_requests/19)

##### Social Street Smart Repository (Chrome Extension)
- [!111 Combined PR for Addition of Rating Mechanism, GPT-3 functionality, and Upgradation of Gulp Version (Open)](https://gitlab.com/aossie/social-street-smart/-/merge_requests/111)
  - [Rating and GPT-3 Functionality Added](https://gitlab.com/aossie/social-street-smart/-/commit/20b64c7c54328525d5b0d720cece68467de1bd9b?merge_request_iid=111)
  - [Added UI for Context analysis](https://gitlab.com/aossie/social-street-smart/-/merge_requests/111/diffs?commit_id=4d2486b4c0fa77041bc5d0632348d7540a1ae2ec)
  - [Upgraded gulp to v4 and changed functional dependencies](https://gitlab.com/aossie/social-street-smart/-/merge_requests/111/diffs?commit_id=34fd45720e338f2ea443aa222580f5e7588421f0)



### Future Scope
- Could enhance extension credibility by implementing a content filtering mechanism with AI-driven credibility scoring, user feedback loop, transparency, and educational resources.
