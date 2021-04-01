# Process.Canvas.Attendance
Convert canvas output on attendance to scores for uploading.
Based on script posted by *murphyl* on Canvas LMS support page.
Original source of code and README info: https://community.canvaslms.com/t5/Admin-Group/Canvas-Assignment-for-Zoom-Attendance/bc-p/452743#M2125

The Python script does three things: (1) create a new assignment, (2) take the provided Zoom meeting report and extract attendees, (3) add a grade to the assignment for students that attended the Zoom meeting

# Initial Configuration

The script uses the Canvas API to create and grade a new assignment. An access token is required to use the API and this will provide the same level of access as your Canvas account.

1. In Canvas, click Account then Settings
   - Scroll down to Approved Integrations and at the bottom of the integrations list, click + New Access Token
2. Provide a purpose and expiry date (N.B. Use <2wks to minimize risk. Do not leave the date blank!) and click Generate Token
3. Copy the access token (When you close this window, you will not be able to view the token again)
4. Open the python script in your favorite text editor or IDE
5. Near the end of the script, 
   a. replace <YOUR API KEY HERE> with your copied access token
   b. A few lines further down, replace <YOUR CANVAS URL> with the URL for your Canvas instance
6. Save the python script



# Usage

1. Preparation: Get the attendance files
2. Run the script using the commandline (recommended) or via the GUI interface
3. Check your results. 
   If you now navigate to the Assignments section of the Canvas site, you will see a new assignment created with the name provided. In the Grades section (if visible to you) this assignment will be graded for all students that attended the Zoom meeting.


## Preparation: Download Meeting Report

To use the script you need to first download a 'meeting report' for each meeting whose attendance you want to evaluate.

1. On your Canvas site, go to the Zoom page and click on Previous Meetings
2. Click Report next to the meeting you want to record attendance for
3. Click Export as CSV File and save to your computer


## GUI Interface

The original code was written with a GUI interface.

1. Run the Python script. You will be prompted for four things (Variable input does slow down script so you could hard code the course ID and points score) :
   a. Course ID (e.g. 3157 (the four digit number in a URL for any page on the course site))
   b. Name for new assignment (e.g. Attendance 7/27)
   c. The Zoom report file (Browse for the saved CSV file)
   d. Point score for present students (e.g. 1)


## Command line (recommended)

1. Run the python script with 

# Issues

- Can't easily troubleshoot since script requires a course ID key.
- 
