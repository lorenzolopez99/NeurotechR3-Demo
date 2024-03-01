# NeuroTechR3 Companion App
![](/report_details.gif)  
During the fall of 2023, I worked in a team of 4 to develop a React-Native mobile companion app for NeuroTechR3. The app allows patients to keep track of their neuro-rehabilitation progress by charting  
exergame scores as well as detailed bio-data for their hand movements. My team and I developed this app from scratch, starting with basic wireframes for user flow and finishing with a fully functional app  
connected to NeuroTechR3's S3 database.

## Background - NeuroTechR3  
![](/ntr3.gif)

NeuroTechR3 develops evidence-based exergame technologies that help clinicians optimize rehabilitation outcomes for individuals with neurological diseases.  
Patients utilize a special camera to capture their hand and wrist movements, allowing them to play motion-based games that function as neuro-rehabilitation therapy.  
I worked under this company along with 3 other developers in order to create a mobile app in the space of 3 months.

## Screens  
This section will break down the app screen-by-screen. App is run via expo on iOS 17 on an iPhone 15 pro, recorded using Apple's native screen recorder, then captured as a GIF using LICEcap.

### Login Screen
![](/login.gif)  

This screen allows the user to login to their account. We use the username and password to connect to the AWS databse, then iterate through every bucket of data corresponding to that user. We parse the JSON to format the data and then store it via AsyncStorage.  
(iOS Screen Capture automatically censors password input)

### Home and Calendar Screens
![](/calendar.gif)

The Home screen is the first thing the user sees as they log in, and displays how many daily tasks are done, as well as a summary of their most played games and total time played.  
Upon tapping the daily tasks, they are taken to a calendar that displays their current streak, as well as every active day. The more a user accomplishes on a day, the brighter the marking for that day.  
On this calendar screen, they can also log their mood and pain status for the day.

### Game Report and Details Screens
![](/report_details.gif)

From the Home Screen, the user can tap on the Summary card to access the Game Report screen, which lists their most recent progress for every game in their records. This screen is modeled after the iOS Health App.  
The user can tap on a specific game to access the Details Screen for that game, which features a video breaking down the targeted movement for that game, as well as detailed graphs for scores and other biodata.

## Modules
This section documents the relevant modules used in the project.

### react-native-async-storage
This module is responsible for asynchronous data storage, and is key to the app's function. Upon logging in, the app checks its cache for data, and updates that cache based on what it pulls from the AWS database.  

### react-native-skia
2D Graphics module, responsible for the graphs displayed on the Game Report Screen. 

### react-native-calendars  
Responsible for the calendar, slightly limited in terms of aesthetic customization.  

### react-native-wagmi-charts  
Line chart module used in the Details Screen.  

### expo-av
Audio-visual module necessary for displaying the videos on the Details Screen.

### rn-pdf-reader  
Responsible for displaying the PDF under the help section.
