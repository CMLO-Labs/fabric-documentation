1.  Create Workspace:
    - After activating the free trail of Fabric, you will be landing to this screen of Fabric where you can create a Workspace.
        - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FuPbqXuSUl2.png.enc?alt=media&token=0c4be9bf-604b-4dda-bd42-6c18b6f7fb35)
    - Open `PowerBI` and click on `Workspaces` present in the tabs list. 
    - **Licence Mode** should be set to `Trial` to access Fabric capacity. (refer image below)
    - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2Fkv533Y5piv.png.enc?alt=media&token=98049bf2-7b37-4569-a080-97db8d9c06b8)
    - Name: `Fabric Training`
    - Now, you will be able to see the new workspace on the sidebar. We can use this workspace to store all our project related objects.
    - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2F5W2UqAMl3v.png.enc?alt=media&token=115c555b-214f-4d46-9ad3-71751e86c87a)
2. Creating a Lakehouse (Common data storage for your artifacts.)
    - To create a Lakehouse, go to `Data Engineering` experience from the bottom left corner of the fabric homepage. (see image)
        - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FZD8wBZuEpR.png.enc?alt=media&token=4908f8a9-076a-4a30-996d-88929029998d)
    - After switching to Data Engineering experience, you can see an option to create a Lakehouse.
        - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2F-1cjuEmdn7.png.enc?alt=media&token=686526c9-999b-4f26-9a25-7c7c02102a5e)
    - Name: `LakehouseTraining`
    - You will also get a SQL endpoint to access the tables inside the Lakehouse.
        - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FrcSD5nQVFD.png.enc?alt=media&token=7b1a666b-1e02-4da6-84d3-85f0d2b5097e)
3. Loading Data into the Lakehouse (Creating DataPipeline) -- __We can use this to periodically load the SEC and other data that is needed by agents into the Lakehouse so it can be accessed by the agents in the downstream tasks.__
    - You can use `Data Pipeline` to load and preprocess your data. (refer to the image) [You should be in `Data Factory` or `Data Engineering` experience to be able to see this option]
        - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FvBgFmkXAPY.png.enc?alt=media&token=90e15483-f95f-4065-ab66-b4dc4c72e872)
    - Name: `DataPipeline1`. This will create an empty pipeline where we can create different activities
        - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2F6PxOo2Gvrl.png.enc?alt=media&token=c827e540-c776-47d1-ab90-9f3d04c2f64d)
    - **Activity-1**: Click on `Copy Data` to copy the data from the source. 
        - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FBG4nX5NMfz.png.enc?alt=media&token=f3b2377f-7a43-4069-ba5f-a975c80a6524)
        - [[Copy Data Settings]] Click on `Use Copy Assistant` to help you pick your data. (Source and destinations for your data)
            - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FLzZPa4Cc0M.png.enc?alt=media&token=d375c413-c857-4619-9417-2f83c740f025)
            - After selecting your source, you will need to provide credentials to connect to that data source. (Connecting to Azure Blob service in the below example)
                - Details of the data:
                - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2Fl95m0XNLCu.png.enc?alt=media&token=a4f8c38c-fe93-4661-ab8b-6da6e9a2b512)
                - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2Fin7u8IYQDC.png.enc?alt=media&token=edd584e4-0c51-46b7-8aef-f9b11b4b6a08)
                - If you get `Unable to list files` pop-up, you need to provide the folder path correctly to view the files in the given blob container.
                - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2Fg9wuAZEIBm.png.enc?alt=media&token=01241e0a-7275-478d-9797-d6cea70ad3e8)
                - You can see the data now: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FSD2fXCEfqy.png.enc?alt=media&token=dbb0764f-f9d0-4736-b555-6052313dad08)
                - Select the table you want to work with: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2Ffc24-rLAXS.png.enc?alt=media&token=a8cf281a-6c14-418d-899f-6b6b2fb17745)
            - Select the lakehouse we created in the previous step as the destination for the data.
                - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FTWYrq2kwFK.png.enc?alt=media&token=4d7f0d82-efd1-4f60-9a25-f86257b8ade8)
                - Check & modify the datatypes and column names etc: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FZknSFn9zgW.png.enc?alt=media&token=9d22c953-187c-4f69-96cc-1b97a18bbeed)
            - Review and save:
                - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FppNdO1F1kM.png.enc?alt=media&token=2afd4943-3513-4f2b-bc2c-50de8a670306)
        - After these steps, Copy Data Activity will be popped-up and running in you data pipeline as shown below:![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2F92sGtr3tBw.png.enc?alt=media&token=929c259b-b647-4900-b906-248fa3df78a4)
        - Once the `Copy Data` activity finishes, you will be able to see the data you loaded in your destination lakehouse: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FaZoq5SlHPZ.png.enc?alt=media&token=c5af99fa-b5ae-493e-aee5-45550c79238a)
    - **Activity-2**: `Dataflow` activity to do the transformations:
        - Add Dataflow activity to the pipeline & now we have to create a new dataflow to define the transformations we need: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2Fn9aGkRsmLb.png.enc?alt=media&token=55983b91-d20e-4b60-825d-48dfe36f111d)
        - Clicking on `New` will take you to a `PowerQuery` like page where you can do all the transformations you need and publish that dataflow.
            - `Get Data`-->`more(to select the lakehouse)` can be used to import the raw table we placed in Lakehouse in the earlier step:![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2F4BB2i19ClJ.png.enc?alt=media&token=6ca9d25c-a8d0-482c-9446-dedd448c35a0)
            - Select the table by navigating to the workspace and the lakehouse you created: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2F_UzvLFHJ6E.png.enc?alt=media&token=d8b55eea-8366-40b2-a3dd-2e7c2244a56c)
            - After finishing the transformations you need, select the Data Destination: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FSqL_dcAdYl.png.enc?alt=media&token=c2157d6a-aa59-43be-83a6-d35e77f446fb)
            - Give a new table name to places the transformed data: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2Fp3H3zG5N8C.png.enc?alt=media&token=10bd3704-e2dc-49f2-badc-d70179a60875)
            - Check and edit the mapping and publish the Dataflow: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FHpAEw_G8iV.png.enc?alt=media&token=71f7a62c-ff70-4ab7-bc99-db23c92f83cb)
        - After a while, the new dataflow will appear in the DataPipeline page. You can add it to the pipeline after the `Copy Data` activity.
    - **__DataFlow activity might be too slow to make the transformations. We can either use `Notebooks` to utilize the power of Spark or do some minor changes in setting to speed-up the DataFlow by a little bit__**
        - Disable `Staging` for a better speed. ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FsSd-rLsVxT.png.enc?alt=media&token=552acca3-bbd9-45e4-bb24-6ff809ecbf91)
    - We can also schedule a pipeline for scheduled loading of our data.
4. Using Notebooks in DataPipeline
    - Connecting to the Lakehouse to access the data within the notebook environment:
        - Within the notebook, you can access the tables/files in your lakehouse by adding the lakehouse to the notebook. ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FJfXyaTC8I6.png.enc?alt=media&token=6f0d795d-a231-4830-aedc-644b7d870d64)
        - You can use the files in your lakehouse inside your notebooks to load the data into dataframes etc. ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FVgHw22Lm2R.png.enc?alt=media&token=25e48938-8e8f-4771-8277-5f9617206d24)
    - We can use Spark to do the transformations needed on the production level data. ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FnR0D9s0tz-.png.enc?alt=media&token=d0945af1-2867-479f-ab17-044bd241505e)
    - We can connect notebooks like these to perform the required transformations and move our data from `Bronze`--> `Silver`--> `Gold` layers. ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2F5yu3jXSkz5.png.enc?alt=media&token=f3a25571-c36f-45bb-8e3f-65a8a0d13e4f)
    - **[[Deploying the notebook as Spark Jobs]]** We can also deploy this as a Spark Job definition to get it production ready.
        - This is the sample spark code that we are using to implement the transformations on our sample data: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FcjzuDhzTIK.png.enc?alt=media&token=9935c941-e5fb-42ec-909b-4c4413bd483e)
        - Define a new spark job definition: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2F2TQbdpaVOq.png.enc?alt=media&token=e586c462-34d2-42f7-bd4c-3aa35f00a3e3)
        - Name: `spark-job-definition1`
        - After giving the name, you will be redirected to fill the spark job definition file. We can upload the above code from local or from ADLS: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2Fd9P85H-6jE.png.enc?alt=media&token=f1469c3a-0b76-46a3-8f7a-d7ff7f238bb8)
        - `lakehouse Reference` mentioned in the spark job definition helps the spark job to refer to a specific lakehouse whenever we write a path inside our spark code: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FT2Fwgs9QNZ.png.enc?alt=media&token=d81a972c-134e-410b-aed1-3470dea9beed)
        - Save and run the spark job to make sure everything works.
    - Instead of notebook, add the spark job to the Data pipeline.
    - We can modify the **[[spark settings]]** within our workspace in the workspace settings tab: ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FTYa-HAy2IU.png.enc?alt=media&token=887f347d-7599-48b5-bb23-74bd6b080b1a)
    - 
5. Sample Autogen based `Investor Relations Agent` notebook orchestration:
    - Pseudocode:
        - ```python
          import pandas as pd
          from autogen import GroupChat, GroupChatManager, AssistantAgent, UserProxyAgent, register_function
          
          # ----------------------------
          # Define Tools and Functions
          # ----------------------------
          def retrieve_golden_data():
              """Retrieves data from the golden data directory."""
              data = pd.read_csv('Files/golden_data/golden_data.csv')
              return data.to_json(orient='records')
          
          llm_config = {
              "cache_seed": 42,  # change the cache_seed for different trials
              "temperature": 0,
              "config_list": [
                  {
                  "model": "<model_name>",
                  "api_key": "<api_key>",
                  "api_type": "<api_type>"
                  }
              ],
              "timeout": 120,
          }
          
          # ----------------------------
          # Define Agents
          # ----------------------------
          user_proxy = UserProxyAgent(
              name='UserProxy',
              system_message="User proxy agent to interact with the chat system.",
              human_input_mode="NEVER",
              description="Coordinates and initiates conversations as the user proxy."
          )
          
          data_agent = AssistantAgent(
              name='DataRetrievalAgent',
              system_message="Agent responsible for retrieving golden data.",
              description="Fetches data from the golden data directory.",
              llm_config=llm_config,
          )
          data_agent.register_for_llm(name="retrieve_golden_data", description= "Gathers most recent data. No input parameter is needed")(retrieve_golden_data)
          user_proxy.register_for_execution(name="retrieve_golden_data")(retrieve_golden_data)
          
          analyst_agent = AssistantAgent(
              name='AnalystAgent',
              system_message="Agent responsible for analyzing data based on the question",
              description="Performs data analysis and provides key insights.",
              llm_config=llm_config
          )
          
          ir_agent = AssistantAgent(
              name='InvestorRelationsAgent',
              system_message="Agent responsible for generating investor relations insights.",
              description="Provides investor relations insights based on data analysis.",
              llm_config=llm_config
          )
          
          # ----------------------------
          # Define Workflow and Group Chat
          # ----------------------------
          
          def select_next_speaker(last_speaker, groupchat):
              messages_list = groupchat.messages
              prev_response = messages_list[-1]['content'] if messages_list else ""
              prev_speaker = messages_list[-1]['name'] if messages_list else None
          
              if prev_response.rstrip().endswith("TERMINATE") and prev_speaker == 'InvestorRelationsAgent':
                  return user_proxy
              return 'auto'
          
          # Create group chat with agents
          groupchat = GroupChat(
              agents=[user_proxy, data_agent, analyst_agent, ir_agent],
              speaker_selection_method=select_next_speaker,
              allowed_or_disallowed_speaker_transitions={
                  user_proxy: [data_agent],
                  data_agent: [analyst_agent],
                  analyst_agent: [ir_agent],
                  ir_agent: [user_proxy]
              },
              speaker_transitions_type="allowed",
              messages=[],
              max_round=10
          )
          
          # Initialize the manager and start the chat
          manager = GroupChatManager(groupchat=groupchat, llm_config=llm_config)
          user_proxy.initiate_chat(
              manager, 
              message="Retrieve and analyze the latest data. Provide key insights for investor reporting."
          )
          ```
    - Stategraph: 
        - ![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2FCMLO_Labs%2FJQF9YzuTZc.png.enc?alt=media&token=303fb621-673a-4d48-b488-cfd83aa5e953)
        - 
