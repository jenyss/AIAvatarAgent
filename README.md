# LangGraph AI Agent for Educational Content with AI Avatar

This AI Agent enables you to create educational video content from a simple text input. You can enter a topic, and the agent will use all or some of the available tools accordingly:

1. Search for reliable information – It gathers relevant sources online to ensure the content is fact-based.
2. Generate a concise script – It creates a structured, engaging script tailored to the given topic.
3. Create a talking avatar video – The script is transformed into a video where a digital avatar presents the information.
4. Download the video – You can save the generated video for personal use.

You can quickly produce AI generated educational videos without any technical expertise. 

If you have any questions or would like to collaborate, feel free to reach out to me on [LinkedIn](https://www.linkedin.com/in/jenya-stoeva-60477249/). You're more than welcome!

## Agent Tools
* **TavilySearch:** Using [Tavily](https://tavily.com/) for semantic and contextual web search. **NOTE:** The Agent determines whether to invoke a tool based on user input. If you want to force a specific tool to be used, modify the ```system_prompt```. For example: **Important: Always use TavilySearch to ensure up-to-date information.**
* **ScriptGenerator:** OpenAI GPT-4o powered.
* **DIDAvatarGenerator:** Calling [D-ID](https://www.d-id.com/) for avatar animation. **Important** Read the D-ID image requirements section!
* **AvatarDownloader:** Local file download tool.

### D-ID image requirements & more
* Public URL ending with the image name. **_You can use GitHub but make sure to take the raw image link!!!_** Example of raw link: https://raw.githubusercontent.com/jenyss/AIAvatarAgent/main/Eli_cat.jpeg<br>

❗ **Warning:** I deleted Eli_cat.jpeg since I didn't want my daughter ending as your avatar.😊 Please take care to substitute the image in the ```generate_avatar``` function. I forgot to expose it as an arg in the main function. You can modify the payload to customize the avatar's speech according to your needs.

* Image size up to 10 MB!
* **Only human faces**, won't work with animal photos!
* **Image resolution matters!** D-ID will fail with high resolution images (at least on the free plan). I tested it with images roughly around 1280x1280 px and it works fine.
* Check [D-ID API](https://docs.d-id.com/reference/createtalk) for the configuration of the avatar which you should pass in the payload of the ```generate_avatar``` function. See TEXTSCRIPT > Provider where you can select the text to speech provider and different languages, personalities, speaking styles, etc

## Intallation

<b>Prerequisites</b>

* Access to <b>JupyterLab, Google Colab</b>, or another interactive computing environment to run this Jupyter Notebook.

### Step 1: Clone the Repository

Clone this repository to your local machine:
```
git clone <REPOSITORY_URL>
cd <PROJECT_FOLDER>
```

### Step 2: Open Jupyter Notebook in JupyterLab

Ensure that ```<PROJECT_FOLDER>``` is accessible in JupyterLab by setting it as your working directory in JupyterLab.
 * In JupyterLab, use the "Open from Path" option to load ```AIAvatarAgent.ipynb```.
 * Similarly, load ```.env``` and populate the variable keys with appropriate values.
 * The first cell in the Notebook installs the required libraries: **%pip install langgraph python-dotenv nest_asyncio**

### Step 3: Run the Jupyter Notebook

To execute the notebook, select each cell and press ```Shift + Enter```.

## Agent Execution Output

================================ Human Message =================================<br>
<br>
Tell me how to grow tomatoes in 50 seconds. Download the video.<br>
================================== Ai Message ==================================<br>
Tool Calls:<br>
  ScriptGenerator (call_oRdIok4LsuIoDMb3CiMRgSKB)<br>
 Call ID: call_oRdIok4LsuIoDMb3CiMRgSKB<br>
  Args:<br>
    __arg1: How to grow tomatoes<br>
================================= Tool Message =================================<br>
Name: ScriptGenerator
<br>
[INTRO]<br>
Welcome to our guide on growing tomatoes. Whether you're a beginner or an experienced gardener, these tips will help you cultivate healthy, delicious tomatoes.<br>
<br>
[SECTION 1: CHOOSING VARIETIES]<br>
Start by selecting the right tomato variety for your climate and space. Determinate types are compact, ideal for containers, while indeterminate types grow larger and need staking.
<br>
[SECTION 2: PLANTING]<br>
Choose a sunny spot with at least 6-8 hours of sunlight. Prepare the soil by mixing in compost or well-rotted manure. Plant seedlings deep, burying two-thirds of the stem to encourage strong root growth.
<br>
[SECTION 3: WATERING]<br>
Water consistently, aiming for 1-2 inches per week. Water at the base to avoid wetting the leaves, which can lead to disease. Mulch around plants to retain moisture and suppress weeds.
<br>
[SECTION 4: SUPPORTING PLANTS]<br>
Use stakes, cages, or trellises to support your plants. This keeps fruit off the ground, reducing the risk of rot and pests.
<br>
[SECTION 5: FERTILIZING]<br>
Feed your tomatoes with a balanced fertilizer every 4-6 weeks. Avoid high nitrogen fertilizers, which promote foliage over fruit.
<br>
[SECTION 6: PRUNING]<br>
Prune suckers, the small shoots between the main stem and branches, to improve air circulation and direct energy to fruit production.
<br>
[SECTION 7: PEST AND DISEASE MANAGEMENT]<br>
Monitor for pests like aphids and caterpillars. Use organic pesticides or introduce beneficial insects. Rotate crops annually to prevent soil-borne diseases.
<br>
[SECTION 8: HARVESTING]<br>
Harvest tomatoes when they are firm and fully colored. Gently twist and pull from the vine. Enjoy them fresh or preserve them for later use.
<br>
[OUTRO]<br>
With these steps, you'll enjoy a bountiful tomato harvest. Happy gardening!<br>
================================== Ai Message ==================================<br>
Tool Calls:<br>
  DIDAvatarGenerator (call_a0OzIMDh1CeTo0GUfccyMdPk)<br>
 Call ID: call_a0OzIMDh1CeTo0GUfccyMdPk<br>
  Args:<br>
    __arg1: [INTRO]<br>
Welcome to our guide on growing tomatoes. Whether you're a beginner or an experienced gardener, these tips will help you cultivate healthy, delicious tomatoes.<br>
<br>
[SECTION 1: CHOOSING VARIETIES]
Start by selecting the right tomato variety for your climate and space. Determinate types are compact, ideal for containers, while indeterminate types grow larger and need staking.
<br>
[SECTION 2: PLANTING]
Choose a sunny spot with at least 6-8 hours of sunlight. Prepare the soil by mixing in compost or well-rotted manure. Plant seedlings deep, burying two-thirds of the stem to encourage strong root growth.
<br>
[SECTION 3: WATERING]
Water consistently, aiming for 1-2 inches per week. Water at the base to avoid wetting the leaves, which can lead to disease. Mulch around plants to retain moisture and suppress weeds.
<br>
[SECTION 4: SUPPORTING PLANTS]
Use stakes, cages, or trellises to support your plants. This keeps fruit off the ground, reducing the risk of rot and pests.
<br>
[SECTION 5: FERTILIZING]
Feed your tomatoes with a balanced fertilizer every 4-6 weeks. Avoid high nitrogen fertilizers, which promote foliage over fruit.
<br>
[SECTION 6: PRUNING]
Prune suckers, the small shoots between the main stem and branches, to improve air circulation and direct energy to fruit production.
<br>
[SECTION 7: PEST AND DISEASE MANAGEMENT]
Monitor for pests like aphids and caterpillars. Use organic pesticides or introduce beneficial insects. Rotate crops annually to prevent soil-borne diseases.
<br>
[SECTION 8: HARVESTING]
Harvest tomatoes when they are firm and fully colored. Gently twist and pull from the vine. Enjoy them fresh or preserve them for later use.
<br>
[OUTRO]<br>
With these steps, you'll enjoy a bountiful tomato harvest. Happy gardening!<br>
🚀 Sending request to D-ID API...<br>
🔎 API Response: {'id': '```DELETED```', 'created_at': '2025-02-02T13:19:13.136Z', 'created_by': 'google-oauth2|113994549', 'status': 'created', 'object': 'talk'}<br>
✅ SUCCESS: Avatar generation request submitted! Request ID: ```DELETED```<br>
🔍 Checking avatar status...<br>
🔎 API Response: {'user': {'features': ['stitch', 'api-keys:write', 'clips:write', 'translation', 'scene', 'premium-plus:skip-speaker-validation', None], ...<br>
⏳ Waiting for processing... Retrying in 10 seconds.<br>
🔎 API Response: {'user': {'features': ['stitch', 'api-keys:write', 'clips:write', 'translation', 'scene', 'premium-plus:skip-speaker-validation', None], ...<br>
✅ SUCCESS: Avatar generation complete! 🎬 Video URL: ```DELETED```<br>
================================= Tool Message =================================<br>
Name: DIDAvatarGenerator<br>
<br>
https://d-id-talks-prod.s3.us-west-2.amazonaws.com/...<br>
================================== Ai Message ==================================<br>
Tool Calls:<br>
  AvatarDownloader (call_kEHrfHirgGEjUMyomkdjvt3S)<br>
 Call ID: call_kEHrfHirgGEjUMyomkdjvt3S<br>
  Args:<br>
    __arg1: https://d-id-talks-prod.s3.us-west-2.amazonaws.com/...<br>
================================= Tool Message =================================<br>
Name: AvatarDownloader<br>
<br>
✅ Download complete: downloads/avatar_video.mp4<br>
================================== Ai Message ==================================<br>
<br>
The video on how to grow tomatoes has been created and downloaded successfully. You can find it saved as `downloads/avatar_video.mp4`. Enjoy your gardening!
