# Lab 10 Notes

# CI Workflow (Part 1)  
CI merges code from developers when they pull. CI will conduct unit tests to make sure everything still works.
<img width="1680" alt="01 java with gradle" src="https://user-images.githubusercontent.com/99227228/168737417-4d53e087-e9ce-4f92-97a4-c279713d39ed.png">

The code from the instruction prompt has been copied and pasted to the gradle.yml file
<img width="1680" alt="02 changes committed to gradle yml" src="https://user-images.githubusercontent.com/99227228/168737648-9dd7ada9-9a2e-46e2-abac-0454ffb0f5d9.png">

I modified the readme markdown. Once committed, this triggers the push and pull request to main from the code earlier.  
This causes an ubuntu image to run, which will build and test these changes using java 11 and gradle. It outputs a jar file, as shown from the given code.  
Since the job completed, this means my build succeeded and CI was successful.
<img width="1680" alt="03 Make a change to the code and commit to main branch to trigger the action  " src="https://user-images.githubusercontent.com/99227228/168737790-0fd3a0b2-b1a7-4394-ad50-be4124bccdd7.png">


# CD Workflow (Part 2)  

I several changes to the google.yml file. As shown below, I changed GKE_CLUSTER to cmpe172 to match my cluster.  
I changed the deployment_name,repository, and image to spring-gumball.  
I also modified it to use secrets: GKE_RPOJECT and GKE_SA_KEY  
<img width="1680" alt="05 google yml" src="https://user-images.githubusercontent.com/99227228/168744162-943d87e0-f697-49ec-beb4-20ad83055be5.png">

I noticed the comments in the given code, in which professor stated to change 4 replicas to 2 replicas:
<img width="1680" alt="06 professor stated he had issues deploying with 4 replicas so change to 2" src="https://user-images.githubusercontent.com/99227228/168744759-cabf8b07-c26b-4629-a6ff-367239fbb9f9.png">

Service account created:  
<img width="1680" alt="07 service account creation" src="https://user-images.githubusercontent.com/99227228/168748146-31a51c87-a581-440d-b011-65112df303db.png">

Key donload as a JSON file:  
<img width="1680" alt="08 json file key" src="https://user-images.githubusercontent.com/99227228/168748216-984939bf-62a7-439b-9580-037a6a42ef03.png">

Key has now been saved:  
<img width="1680" alt="09 key saved" src="https://user-images.githubusercontent.com/99227228/168748272-7ea7e255-1fff-4df0-85f8-43ef834d688e.png">

Key shown in Dashboard:  
<img width="1680" alt="10 keys dashboard" src="https://user-images.githubusercontent.com/99227228/168749603-53449c4c-b617-44f5-96f9-07b776727a63.png">

GKE_PROJECT and GKE_SA_KEY have been added to my Github repo secrets:  
<img width="1680" alt="11 secret keys added" src="https://user-images.githubusercontent.com/99227228/168749650-939a543e-df31-452d-91a5-c59a2a890765.png">

A release should trigger CD:  
<img width="1680" alt="12 release triggers CD" src="https://user-images.githubusercontent.com/99227228/168749676-5bc67899-3227-4bdb-b09e-75b7c7406eaf.png">
