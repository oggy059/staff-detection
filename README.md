# staff-detection
Trying to detect the staff (wearing nametag) as an evaluation test from Footfallcam. These texts are copied directly from their test.

A person is identified as a staff if he/she is wearing a staff name tag, as shown below.

![image](https://github.com/oggy059/staff-detection/assets/746455/c9136345-c189-4b54-8f08-2511d539e7a7)

As an AI Engineer, you have a few hundred of video samples from our 3D sensor. Here, you are given 1 sample
(“sample.mp4”) which is the view from our 3D sensor. Within the clip, there is a person wearing the tag and walking
along the corridor. Below are 2 snapshot instances of the person, all other people are not wearing the tag:

![image](https://github.com/oggy059/staff-detection/assets/746455/348f5f17-79a3-4592-bf64-090fec1cc093) ![image](https://github.com/oggy059/staff-detection/assets/746455/66ba9ebf-26c3-41d8-8bf5-044fe3e0fe5c)

Tasks:
1. Identify which frames in the clip have the staff present?
2. [Bonus] Locate the staff xy coordinates when present in the clip.

Instructions:
- Be creative! Make assump􀆟ons when needed
- Free to use any tool, programming language, model to complete the task
- Use illustration or visualization aids when possible
- Submit a 1-2 page documentation on your solution, highlight the key parts
- Submit your code script or repository link, if any
- Be prepared to explain your solu􀆟on during interview, and run your code on your laptop using another test video
on the spot

My solution:

The proposed solution for the first and second questions is as follows:

1) Detect every person in the video.
2) Track and assign a unique ID for each person.
3) Index their bounding box’s x and y axes coordinates.
4) Crop every person according to their bounding box and label them according to the number
of frames and unique ID.

To accomplish these steps, different techniques are used:
• YoloV5: 1 and 3
• DeepSORT: 2

For the results, shown in the screenshots below, the staff (person wearing the tag) is detected and assigned ID number 48 on the left and ID number 116 on the right.
![image](https://github.com/oggy059/staff-detection/assets/746455/ccbeb9a3-4b42-4bb4-ae7a-cc549f65d6e1)![image](https://github.com/oggy059/staff-detection/assets/746455/4af88ec1-4238-49b8-bf1e-7b6cf8aa12b0)

However, the tracker is not perfect as the staff was assigned different IDs when he is walking and another different IDs when wearing the black jacket.

- The ID when not wearing the jacket: 48,64,65,71, 83.
- The ID when wearing the jacket 102,113,116,121,131,138.
- The frames where the staf f is detected while walking according to ID number:
  - ID 48 366 392
  - ID 64: 446 475
  - ID 65: 452 469
  - ID 71: 525 564
  - ID 83: 593 594
  - ID 102: 829 866
  - ID 113: 913 933
  - ID 116: 936 94 4
  - ID 121: 992 1055
  - ID 131: 1080 1127
  - ID 138: 1178-1305

The coordinates of x and y axes are in the Excel file.

