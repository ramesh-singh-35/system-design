## GOOGLE DRIVE ##

1. 2 API endpoints are required.

1. Upload a file: https://api.example.com/file/upload
Params: Path, local file to be uploaded.
   
2. Download a file:  https://api.example.com/file/download
Params: Path of file to be downloaded: path: "src/resources/config.xml"
   
3. Get file versions: https://api.example.com/file/versions, can sent paginated results.
Params: file path and name.
   
Block servers:
1. Upload file to cloud storage in blocks, can only upload updated blocks using sync algorithms.
2. Compressed blocks and encrypts them before sending to cloud storage.

Metadata DB.
Different tables we can have in metadata database:

1. User
2. Device
3. Block
4. File_version
5. File
