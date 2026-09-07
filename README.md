Metadata-Extraction-using-ExifTool-log2timeline-and-Hidden-Data-Search-using-Steganography-Tools
## AIM:
To extract metadata, perform timeline analysis, and search for hidden data using forensic tools like ExifTool, log2timeline, and steganography detection tools.
## REQUIREMENTS
- **Operating System:** Kali Linux (preferred) or any Linux distro with forensic tools
- **Tools:**
     -  ExifTool – For metadata extraction
     -  plaso/log2timeline – For timeline analysis
- **Steganography tools:** steghide, zsteg, binwalk
- **Test Data:** Image, video, and document files (some with embedded hidden data)
## ARCHITECTURE DIAGRAM
```mermaid
flowchart TD
    A[Sample Files - Images, Videos, Documents] --> B[Metadata Extraction with ExifTool]
    B --> C[Event Timeline Creation with log2timeline]
    C --> D[Hidden Data Search with Steganography Tools]
    D --> E[Evidence Analysis and Documentation]
```
## DESIGN STEPS:
### Step 1:
Use exiftool to extract metadata from files such as images, documents, and videos.

### Step 2:
Use log2timeline and plaso to create and analyze event timelines from system logs and file metadata.

### Step 3:
Apply steganography detection tools like steghide, zsteg, or binwalk to uncover hidden data in media files.

## PROGRAM:
| Step | Action                  | Tool                 | Output                           |
| ---- | ----------------------- | -------------------- | -------------------------------- |
| 1    | Extract file metadata   | ExifTool             | Metadata fields, GPS, timestamps |
| 2    | Generate event timeline | log2timeline / plaso | CSV/HTML timeline                |
| 3    | Search for hidden data  | steghide / binwalk   | Extracted hidden files           |
| 4    | Document findings       | Manual report        | Investigation record             |


## OUTPUT:
### A. Using ExifTool – for file metadata
- **Install:**
```bash
sudo apt update
sudo apt install exiftool -y
```
- **Extract metadata from a file:**
```bash
exiftool image.jpg
```
- **Batch process a folder:**
```bash
exiftool -r /path/to/folder
```
- **Useful flags:**
  
- ```-G: Show metadata group```

- ```-time:all: Show only timestamps```

- ```-GPSLatitude -GPSLongitude: Extract GPS data```



### install log2timeline
```
sudo apt install plaso -y
```

```
sudo apt install steghide -y
```
- **Embed data**
```
steghide embed -cf /home/kali/Downloads/wallpaper.jpg -ef /home/kali/Downloads/secret.txt
```


- **Extract hidden data:**
```
steghide extract -sf hidden.jpg

```


### Using binwalk – for file analysis
```bash
sudo apt install binwalk -y
binwalk suspicious.jpg
```
```bash
binwalk /home/kali/Downloads/wallpaper.jpg
```
### OUTPUT
<img width="1394" height="1128" alt="IMG 1" src="https://github.com/user-attachments/assets/a7a2839e-67da-487a-93f7-c1a8548b2705" />
<img width="1394" height="1128" alt="IMG 2" src="https://github.com/user-attachments/assets/3e2f46b3-9dbf-4a47-8548-219e7b7ac6a7" />
<img width="2170" height="725" alt="IMG 3" src="https://github.com/user-attachments/assets/1adada0c-e8d1-4113-92d3-d05a1875dae1" />
<img width="1466" height="1073" alt="IMG 5" src="https://github.com/user-attachments/assets/c329e8d3-10ca-4dbe-8a39-630513e8aa1d" />
<img width="748" height="411" alt="IMG 8" src="https://github.com/user-attachments/assets/b5a4cbcf-d42f-4d45-a77f-6526cc098e98" />
<img width="702" height="409" alt="IMG 9" src="https://github.com/user-attachments/assets/e77ad18a-7fdc-42ad-bec0-a779893730e7" />
<img width="703" height="505" alt="IMG 10" src="https://github.com/user-attachments/assets/942f7d75-afa0-4c3c-b6cd-f2354f160ca3" />
<img width="1467" height="1072" alt="IMG 7" src="https://github.com/user-attachments/assets/f4a04c97-8b45-4a0d-9b8c-a44865ac4b81" />






## RESULT:
Metadata was successfully extracted, timeline analysis was completed, and hidden data was identified using steganography tools.
