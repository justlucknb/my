from google.oauth2 import service_account
from googleapiclient.http import MediaIoBaseDownload,MediaFileUpload
from googleapiclient.discovery import build
import pprint
import io
import base64 
image = open('1.jpg', 'rb') #open binary file in read mode
im1 = image.read()
imen = base64.encodebytes(im1)


g = open("out.jpg", "w")
g.write(base64.decodebytes(imen))
g.close()




pp = pprint.PrettyPrinter(indent=4)
SCOPES = ['https://www.googleapis.com/auth/drive']
SERVICE_ACCOUNT_FILE = '***.json'
credentials = service_account.Credentials.from_service_account_file(
        SERVICE_ACCOUNT_FILE, scopes=SCOPES)
service = build('drive', 'v3', credentials=credentials)
results = service.files().list(pageSize=10,
                               fields="nextPageToken, files(id, name, mimeType)").execute()
pp.pprint(results)

folder_id = '**'
name = 'app.py'
file_path = 'app.py'
file_metadata = {
                'name': name,
                'parents': [folder_id]
            }
media = MediaFileUpload(file_path, resumable=True)
r = service.files().create(body=file_metadata, media_body=media, fields='id').execute()
pp.pprint(r)
