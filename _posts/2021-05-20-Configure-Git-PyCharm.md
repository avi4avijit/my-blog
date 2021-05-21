---
layout: post
title:  "Configure PyCharm with Git"
date:   2021-05-20 17:46:41 +0530
categories: Software
---

# Create workspace in PyCharm and configure with Git Repository

1. Open PyCharm. Go to File -> NewProject.. 

![image](https://user-images.githubusercontent.com/39100362/119184087-8c7e2180-ba92-11eb-93e6-c56083a0ad80.png) ![image](https://user-images.githubusercontent.com/39100362/119184108-97d14d00-ba92-11eb-8a8a-55ce30607c26.png)


2. Provide the location (folder path). If the folder is not there, it will be created autometically.
3. The project will be created as per the folder name.
4. Now configure the remote Git location. Go to VCS -> Enable Version control integration...

![image](https://user-images.githubusercontent.com/39100362/119178661-a23c1880-ba8b-11eb-9026-157037826f10.png) ![image](https://user-images.githubusercontent.com/39100362/119178795-ce579980-ba8b-11eb-852e-9437acf1ed08.png)

5. Select **Git** from drop down and click OK.
6. Now Go to again VCS -> Git -> Remote..
7. Provide 
```
      Name: orogin
      URL : https://github.com/avi4avijit/python-basics
```
8. Click OK and again OK. 

![image](https://user-images.githubusercontent.com/39100362/119179618-c3513900-ba8c-11eb-8a1c-b11fe9a43286.png)

![image](https://user-images.githubusercontent.com/39100362/119179669-d49a4580-ba8c-11eb-8d68-302cb8f5b825.png)  ![image](https://user-images.githubusercontent.com/39100362/119179694-df54da80-ba8c-11eb-9756-e7b53a64edf1.png)

9. Right Click on the project. Goto Git -> Repository -> Pull..
10. Click on Refresh Icon and 'Branches to merge' will populate. 
11. Select 'origin/master'. Click **Pull** 

![image](https://user-images.githubusercontent.com/39100362/119180469-f811c000-ba8d-11eb-9c14-8a7dd15a58cb.png)  ![image](https://user-images.githubusercontent.com/39100362/119180605-20012380-ba8e-11eb-8a22-bb7fd2fcb11d.png)

12. Right Click Project and click on 'Syncronize<project name>'
  
![image](https://user-images.githubusercontent.com/39100362/119180773-5a6ac080-ba8e-11eb-8915-ddf15545a960.png) ![image](https://user-images.githubusercontent.com/39100362/119180820-69ea0980-ba8e-11eb-878a-b6d6ab8771ed.png)

13. The Python file 'file_reader.py' will appear under project. 
14. Right Click the file and select **Run 'file_reader' **
15. The output will be printed in console.
  
![image](https://user-images.githubusercontent.com/39100362/119181132-cd743700-ba8e-11eb-803d-a5c0b1c39382.png) ![image](https://user-images.githubusercontent.com/39100362/119181159-d402ae80-ba8e-11eb-98b1-8e38b51ff814.png)


   


