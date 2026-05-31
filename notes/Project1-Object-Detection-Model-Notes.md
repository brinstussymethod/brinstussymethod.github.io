### These notes are later to be added to my projects.html files for documentation 


- Concepts Learned
  
  - YOLO
    - Object detection Machine Learning Algorithm
    - Checkout slides from YOLO ()
  - Creating a Data Set
    - By using [Label Studio] (https://labelstud.io/) to label images that are taken for the model (not using my own images for this model) 
    - Use 100 - 200 images for a starting model
    - Versitial backgrounds, settings, and lighting conditions similiar to what the model will see in an acutal application
      
  - Hosting a labeling tool locally on my computer inside an environment to store on the machine locally instead of using a cloud.
    - Benefits
      - Performance is more efficient for small to medium sized projects
      - independene from the public cloud
      - security of sensitive training data
              
  - Ideas Grasped from the Google Co-Lab [Google Co-Lab Reference] (https://colab.research.google.com/github/EdjeElectronics/Train-and-Deploy-YOLO-Models/blob/main/Train_YOLO_Models.ipynb#scrollTo=0c5Kdh0GmQHS)
    - Using Google Co-Lab to run a gpu in the cloud to train our model
    - Train Test Split Data 
    - Creating a training configuration file
    - Picking the correct YOLO model
    - You Generally want to pick a model that is small enough to meet the speed requirments for the application and still being accurate enough to detect objects
    - We are using
    - Using the correct amount of Epochs
    - Using the amount of epochs sets how long the model will train for
    - according to the youtube video < 200 images 60 epochs is a good starting point. > 200 images a good starting point would be 40 epochs.  
    - How to use model once trained transferring from google co-lab to local-device
    - 
  - Installing Pytorch Correctly NVIDIA GPU [Pytorch Installation] (https://pytorch.org/get-started/locally/)
  - Installing a script online using the `curl` command

- Tools Websites & Datasets Used
  - [Dataset V7] (https://storage.googleapis.com/openimages/web/index.html) 
  - [Roboflow Universe] (https://public.roboflow.one/)
  - [Label Studio] (https://labelstud.io/)
  - [Anaconda] (https://www.anaconda.com/download) (environment tool)
  - [Data Set Used] (https://universe.roboflow.com/vic-bukru/people-detection-nhwbv) [x] Not used anymore
  - [Ultralytics] (python library used to train the model)
  - [Google Co-Lab Reference] (https://colab.research.google.com/github/EdjeElectronics/Train-and-Deploy-YOLO-Models/blob/main/Train_YOLO_Models.ipynb#scrollTo=0c5Kdh0GmQHS)
  - [Youtube Video that Inspired Idea] (https://www.youtube.com/watch?v=r0RspiLG260)
  - We are using the YOLO 11s for the training process

- CLI Used
  - Anaconda
    - conda create --name yolo-env1 python=3.12 (create an encvironment) 
    - conda activate yolo-env1 (activate an environment)
 
  -Pip
    - pip install label studio
    - pip install ultralytics
    - pip3 install torch torchvision --index-url https://download.pytorch.org/whl/cu132
    - pip uninstall torch torchvision torchaudio (wrong pytorch installed "too new apparently")
    - 
  
  -Label Studio
    - Tips
      - If you have more than 1,000 images it's strongly recommended link a local storage folder or cloud account to the project [Local Storage Documentation Local Studio] (https://labelstud.io/guide/storage_local)
    
    -label-studio start
  -curl
    -curl -o yolo_detect.py https://www.ejtech.io/code/yolo_detect.py

## Bugs & Issues
  - Getting this error by windows when trying to upzip my dataset: path is too long.
    - Tried to solve by using admin powershell command New-ItemProperty -Path `"HKLM:\SYSTEM\CurrentControlSet\Control\FileSystem" -Name "LongPathsEnabled" -Value 1 -PropertyType DWORD -Force` and restarting computer
        - FAILED Unknown Reason
    - Gave up and just skipped the files that are too long to export (this might cause issues when training we will see).
  - Huge error prompted when installing label studio on in my python envioronment, seems to be installed successfully so I will ignore it. (hopefully will not cause issues). Seems to be an issue with their own code when installing libraries? `raise InvalidRequirement(str(e)) from e pip._vendor.packaging.requirements.InvalidRequirement: Expected semicolon (after name with no version specifier) or end PasteScript==dev,>=1.6.3dev-r7326`
      - Turns out I just forgot the "-" in label-studio when installing it smh.
  - Error: (yolo-env1) C:\Users\Brian\Documents\Data-Science-Machine Learning\brinstussymethod.github.io\Project-Code\People-Detection-Model\my_model>curl -o yolo_detect.py https://www.ejtech.io/code/yolo_detect.py
                        % Total    % Received % Xferd  Average Speed  Time    Time    Time   Current
                                 Dload  Upload  Total   Spent   Left   Speed
                                    0      0   0      0   0      0      0      0                              0
                          curl: (35) schannel: next InitializeSecurityContext failed: CRYPT_E_NO_REVOCATION_CHECK (0x80092012) - The revocation function was unable to check revocation for the certificate.
          Solution:
                    curl --ssl-no-revoke -o yolo_detect.py https://www.ejtech.io/code/yolo_detect.py (skipping the revocation step)
    Q: Is skipping the revocation step bad? 
    It's a minor risk, and in this context probably fine. Here's the honest breakdown:
    What revocation checking does:
    It verifies that the server's SSL certificate hasn't been revoked (e.g., because the site was compromised or the cert was stolen). It's a safety net against man-in-the-middle attacks using a revoked cert.
    
  - Unable to read frames from the camera. This indicates the camera is disconnected or not working. Exiting program.
    Average pipeline FPS: 0.00
  - Seems like the pytorch I installed for my GTX 1070 TI is not the correct one... 
    C:\Users\Brian\miniconda3\envs\yolo-env1\Lib\site-packages\torch\cuda\__init__.py:384: UserWarning: Found GPU0 NVIDIA GeForce GTX 1070 Ti which is of compute capability (CC) 6.1.
    The following list shows the CCs this version of PyTorch was built for and the hardware CCs it supports:
    - 7.5 which supports hardware CC >=7.5,<8.0
    - 8.0 which supports hardware CC >=8.0,<9.0 except {8.7}
    - 8.6 which supports hardware CC >=8.6,<9.0 except {8.7}
    - 9.0 which supports hardware CC >=9.0,<10.0
    - 10.0 which supports hardware CC >=10.0,<11.0 except {10.1}
    - 12.0 which supports hardware CC >=12.0,<13.0
    Please follow the instructions at https://pytorch.org/get-started/locally/ to install a PyTorch release that supports one of these CUDA versions: 12.6
      _warn_unsupported_code(d, device_cc, code_ccs)
    C:\Users\Brian\miniconda3\envs\yolo-env1\Lib\site-packages\torch\cuda\__init__.py:502: UserWarning:
    NVIDIA GeForce GTX 1070 Ti with CUDA capability sm_61 is not compatible with the current PyTorch installation.
    The current PyTorch install supports CUDA capabilities sm_75 sm_80 sm_86 sm_90 sm_100 sm_120.
    If you want to use the NVIDIA GeForce GTX 1070 Ti GPU with PyTorch, please check the instructions at https://pytorch.org/get-started/locally/
    Solution: I just used an older version of Pytorch (CUDA 12.6) 
<details>
<summary>Click to expand</summary>

### Original Ideas During Project Research
  -I noticed thast it takes a while to label everything manually using the Label Studio tool. I was wondering if there is way to automate this. 

</details>
