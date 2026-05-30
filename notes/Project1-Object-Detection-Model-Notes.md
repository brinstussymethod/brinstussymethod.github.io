### These notes are later to be added to my projects.html files for documentation 


- Concepts Learned
  - YOLO
    - Object detection Machine Learning Algorithm
    - 
  - Creating a Data Set
    - By using [Label Studio] (https://labelstud.io/) to label images that are taken for the model (not using my own images for this model) 
    - Use 100 - 200 images for a starting model
    - Versitial backgrounds, settings, and lighting conditions similiar to what the model will see in an acutal application
      
  - Hosting a labeling tool locally on my computer inside an environment to store on the machine locally instead of using a cloud.
    - Benefits
      - Performance is more efficient for small to medium sized projects
      - independene from the public cloud
      - security of sensitive training data  

- Tools & Websites Used
  - [Dataset V7] (https://storage.googleapis.com/openimages/web/index.html) 
  - [Roboflow Universe] (https://public.roboflow.one/)
  - [Label Studio] (https://labelstud.io/)
  - [Anaconda] (https://www.anaconda.com/download) (environment tool) 


- CLI Used
  - Anaconda
    - conda create --name yolo-env1 python=3.12 (create an encvironment) 
    - conda activate yolo-env1 (activate an environment)
 
  -Pip
    -pip install label studio
  
  -Label Studio
    - Tips
      - If you have more than 1,000 images it's strongly recommended link a local storage folder or cloud account to the project [Local Storage Documentation Local Studio] (https://labelstud.io/guide/storage_local)
    -label-studio start


<details>
<summary>Click to expand</summary>

### Original Ideas During Project Research
  -I noticed thast it takes a while to label everything manually using the Label Studio tool. I was wondering if there is way to automate this. 

</details>
