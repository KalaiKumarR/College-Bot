# College-Chatbot

Step 1: Create new enveronment

Step 2: Downloaded the  rasa dependences -> pip install rasa[full] in cmd

Step 3: Download the simple bot called mood bot -> rasa init (kept as base of my bot)

Step 4: Modify the nlu.yml file which is under the folder name called data
             1.add the possible faq question(example) which may the user ask for the particular under the intent section 
             2.gave the name of the intent for each example which is shown as below
    [- intent: chairman
  			examples: |
    			- chairman?
    			- chairman
    			- who is the owner of bit?
    			- owner of bit?
    			- who is the chairman of this college?
    			- who is the chairman of bit?
    			- who is the chairman of bannari amman institute of technology?
    			- owner of bannari amman institute of technology]

Step 5: Modify the stories.yml which also under the data folder
           1.created the story for indent and created the action which is shown as below
		[- story: chairman name
			  steps:
			    - intent: chairman
 			    - action: utter_chairman]

Step 6: Modify the domain.yml file which is under the test folder
           1.Entered the intent which is created in nlu.yml
           2.Added the response for the particular action which is created in stories.yml  which is shown below
              [utter_chairman:
                  - text: "Thiru S V Balasubramaniam"]

Note: I haven't created custom actions for my bot [will be coming soon...........]

Step 7: Modify the pipeline under the config.yml file 
          1.Add the FallbackClassifier to respond[default message] some of quries which is not trained in nlu.yml and fixed the threshold as 0.3  
          (if confidence level <= threshold ) prints the default massage

Step 8: Train the nlu file using rasa train and it will store the trained model in model folder

Step 9: Test bot using -> rasa shell in cmd

Step 10: Start the server action using  rasa run -m models --enable-api --cors "*"
          Note:Since this Chat UI communicates with the Rasa server using `rest` channel

Step 11: Open the html file in web browser

Step 12: Clicked the chat icon and have some fun with the bot :)
