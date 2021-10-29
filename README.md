# Use_kaggle_data_in_colab
使用kaggle API在colab中下載資料集

先下載kaggle.json金鑰
kaggle > My Account > create new API token



api_token = {"username":"XXXX","key":"XXXXX"}
import json
import zipfile
import os
 
if not os.path.exists("/root/.kaggle"):
    os.makedirs("/root/.kaggle")
 
with open('/root/.kaggle/kaggle.json', 'w') as file:
    json.dump(api_token, file)
!chmod 600 /root/.kaggle/kaggle.json
 
if not os.path.exists("/kaggle"):
    os.makedirs("/kaggle")
os.chdir('/kaggle')

#從要抓資料集的檔案 copy API command
!kaggle datasets download -d shaunthesheep/microsoft-catsvsdogs-dataset

!ls /kaggle


#解壓縮dataset.zip
!unzip 'zip位置' -d '目的地'
