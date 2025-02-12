# Lab Resources

**[↤ Return to Table of Contents](readme.md#table-of-contents)**

## Slack

[Slack](https://lighthall-lab.slack.com/) will be used as the primary means of lab communication, such as general lab announcements (`#-general`), sharing links, sharing and/or discussing papers (`#-papers`), and any day-to-day message that can be sent without email. There's also a channel for keeping notes from our lab meetings (`#-lab-meetings`), as well as channels for specific projects (e.g. `#econdec`).

Try to keep each channel on topic, so that people can subscribe only to the channels that concern them. For messages to one person or a small group of people, use the direct message channels.

All lab members should install Slack to their computers and/or phones and check it regularly. Full-time lab members should also enable notifications for "Direct messages, mentions, & keywords", and select "Notify me about threads I'm following". Please consider allowing Slack updates on your phone and setting do-not-disturb mode for evening and night hours. You are not expected to *always* be reachable, but this configuration should be a reasonable middle-ground.

## Email

Although Slack is convenient for day-to-day communication and group discussions, we should consider it unsecure. Any sensitive communications should be conducted via secure official channels, which is where your UCF.edu email address comes in. If you are  unsure whether it is appropriate to share something in Slack, feel free to use UCF Email. Communications that are only appropriate to have through secure Email might include:

- exchanges of anyone's confidential or otherwise sensitive information, include your own and other lab members'
- identifiable information about participants (names, contact info, etc.), especially in tandem with scheduling information

Other email address domains such as Gmail, etc., should also be considered unsecure for the above communications. We do have a lab email account that goes to only the lab manager(s), PhD students, and Nichole: `lighthall-lab@gmail.com`.

## GitHub

All projects that involve programming of any kind must use some form of version control. We have a [GitHub organization](https://github.com/lighthall-lab/) set up, allowing you to sync your code to the cloud and share it easily with other lab members.

Hosted on the lab's GitHub, you'll find a tutorial repository on the basics of using git for version control, and there is a `#-github` channel in Slack for questions, sharing, and discussion. We will also use GitHub for sharing script examples and hosting lab toolboxes for general use.

## Google Calendar

Google Calendar is used to host a general lab calendar (AD&D Lab), as well as several calendars for individual testing rooms and for project scheduling.

## Google Drive

The [AD&D Lab](https://drive.google.com/drive/folders/0BzClebUy65WlbVRGS2JFcTVuR0E?usp=sharing) folder on Google Drive is used to store documents and files for general use and remote access. It contains a running schedule of lab meeting presenters and topics, and a roster with lab members' contact information. This is primarily so that you can access this information from your mobile devices as needed; you are encouraged to install the Google Drive app if you do not already use it.

## Network Drives

As a UCF student/employee, you will have access to the UCF shared network resources under your NID credentials. As long as you are connected to the `UCF_WPA2` wireless network, or use the [UCF VPN](https://secure.vpn.ucf.edu/) to connect to the university network from home. When connected to the UCF network, you can access the Network Drives in two ways.

First, find the server address ([see here](#server-addresses)) of the resource you are trying to access. Then decide whether you want to access it by mounting it as a network drive on your computer (semi-permanent), or navigate to it directly (temporary).

### Direct Navigation

1. In your computer's file browser, type the network resource's server address directly into the address bar. `\\net1110.net.ucf.edu\`...
2. Sign in with your UCF NID, prepended by `net\` if on Windows, i.e.: `net\xy123456`

### Mount as a Network Drive

- Windows
  1. Right click on "This PC" and select "Map network drive..."
  2. Choose a drive letter (We use "R:") and enter the network resource's server address: `\\net1110.net.ucf.edu\`...
- Mac
  1. Cmd+K to open the "Connect to Server" dialog.
  2. Enter the network resources server address as a Samba protocol address: `smb://net1110.net.ucf.edu/`...

### Server Addresses

Personal Storage: `\\net1110.net.ucf.edu\profiles\[Your NID]`

> This 30GB storage space is accessible only to you, from any computer operating on the UCF local network, or via tunnelling in with the VPN. On IT-managed computers, it is automatically mounted for you as the `U:/` drive. I recommend using it for personal files, API keys, supporting configuration files, etc., that you will use on such computers.

Research Drive: `\\net1110.net.ucf.edu\research2\Lighthall_Lab\`

> The "Research Drive" is our **secure UCF server** that houses all of our experiments, including stimuli, data, and analyses. You should have full access to this drive once the lab managers have completed your orientation and onboarding procedures, and it should appear as the `R:/` drive on any of the lab's IT-managed computers. If it does not, consult the lab staff so they can request IT grant you access.

#### Structure of the Research Drive

I encourage you to become very familiar the Research Drive's directory structure - you will be accessing it quite often. Our allocation is structured like this:

- `_archive`
  - For old stimuli, datasets, analyses, out-of-date code, or anything else that's not being used anymore.
  - Deleting files from the Research Drive cannot be undone (*there's no "Recycle Bin"!*), so moving things here that you don't need anymore is the preferred method for disposal unless you are **1000% sure** you won't need it anymore.
  - This stuff is first on the chopping block when we need to save space on the Research Drive.
- `_working`
  - For stuff you're - *drumroll, please!* - working on, that doesn't quite belong anywhere else.
- `apps`
  - Source code for various code toolboxes and utilities you may need to use.
  - You might be pointed here if you need to use one of the ones we already store here, but you are also welcome to store anything here in its own directory if you think you and/or others might find it useful.
  - If you do find a package or utility you want to store here, put it here in its own directory using `git clone` or another method, and feel free to work on it here.
- `docs`
  - `user`
    - For any small files and documents you're working on for yourself that you need somewhere to store, feel free to create a folder in here with your name/initals/whatever.
    - Please don't abuse this storage by putting large files in here. Anything you put in here is also viewable to anyone else with access to the Research Drive, so don't store any sensitive or confidential information here.
  - `resources`
    - Tutorials, templates, recruitment materials, forms, etc., for example:
    - `lab-manual`
    - `guides`
      - `Git-Version-Control-Tutorial`
      - `Image Processing`
    - `textbooks`
    - `papers`
    - `meetings`
    - `llrn`
      - Resources for the *Learning & Longevity Research Network*
- `experiments`
  - Individual folders for each project, with structure like so:
  - `project-name`
    - `docs`
      - `protocol`
      - `irb`
    - `deploy`
      - Shortcuts, numbered and clearly named, in the order they appear on the study's exam protocol, pointed at the necessary files in `stimuli`, for easy deployment at the time of data collection.
    - `stimuli`
      - All stimuli should be stored here: stimulus images, paradigm scripts, configuration files, etc. When appropriate, such as when the `deploy` directory shortcuts are not working, the experiment should be run directly from these files.
    - `sourcedata`
      - All raw datafiles created by the experiment paradigm when data is collected, in individual subject folders.
      - Unless absolutely necessary, we should *never* directly manipulate the structure or content of datasets here. Instead, we should develop pipelines (`code`) for extracting data from here, transforming it, and loading it into `derivatives`.
      - The preferred structure for datasets is the [BIDS](http://bids.neuroimaging.io/) standard structure with individual folders for each subject:
        - `sub-101`
        - `sub-102`
        - `sub-201`
          - `beh`
          - `anat`
          - `func`
    - `code`
      - All code being used to extract, clean, merge, transform, analyze, etc., any of the project's data should be stored here, and kept as organized and tidy as possible, containing a README.md file that describes as much info as possible about the study and pipeline.
      - Code organization and tidyness might include giving your files descriptive, concise names, sorting pipeline steps into folders, appending your filenames with step numbers (e.g., `1.extract.sh`,`2.tranform.py`), etc.
      - This directory should always be a local git repository pointed to a remote repository `origin` on the [Lab GitHub](https://github.com/lighthall-lab/)
    - `derivatives`
      - All analysis files, intermediary data transformations, figures, etc., should go here.
      - Data pipelines should only **ever** write data into this folder or its subfolders, and it should be kept well-organized and tidy just as the `code` is.

## University, College, and Department Resources

[under construction]

## Graduate Students

In addition to all of the [above](#lab-resources):

- [College of Graduate Studies](https://graduate.ucf.edu/)
  - [Pathways to Success workshops](https://graduate.ucf.edu/pathways-to-success/)
  - [Funding Opportunities](https://graduate.ucf.edu/funding/)
- [Career Services](https://career.ucf.edu/)
- HFCP Program Resources
  - Important Contacts
- etc.?

## Undergraduate Students

In addition to all of the [above](#lab-resources):

- [Office of Student Involvement](https://osi.ucf.edu/)
- [Office of Undergraduate Research](https://our.ucf.edu/)
- [Career Services](https://career.ucf.edu/)
- etc.?

### Undergraduate research

[under construction]

***[to-add]**: information about fellowships, presentation resources, undergraduate opportunities, conferences, etc.*

Undergraduate research assistants play an important role in our lab, and we have a few opportunities for them to earn money or credit for their contributions. Because these opportunities require a certain degree of commitment from both the student and the lab, we generally reserve them for students who have already spent at least one semester volunteering in lab. If this policy would prevent you from being able to work in lab, please talk to me or the lab manager because we want all students to be able to pursue their research interests.

In addition to volunteering in lab, other research opportunities include:

1. If you want to work in lab and earn course credit, you can sign up for independent study or undergraduate research ([link to info]). We will have to fill out a syllabus contract at the beginning of the semester. Typically you would be in lab for at least 10 hours a week, and you would also be required to attend lab meetings, present at one of them, and write a short statement about your experiences at the end of the semester. Note that you can enroll in research courses multiple times.
2. If you want to work in lab and earn money, you can apply for an ([undergraduate research fellowship]). Candidates are expected to be academically strong (typically, GPA of 3.4 or above), and you would be expected to work 12-15 hours per week. Because these fellowships are intended to support your academic development, URF students will be strongly encouraged to participate in lab meetings. Note that if you have another UCF job, you're not allowed to work more than 20 hours per week during the academic year, and that includes the URF hours (which will also count toward work-study).
3. If you want to work in lab, earn money, and are eligible for work-study, there may be other paid research opportunities available.

If you're an undergraduate student and you want to pursue any of these options, talk to Nichole or the lab manager(s).

### External Research Opportunities and Fellowships

[NSF Graduate Research Fellowship](https://www.nsfgrfp.org)

The NSF GRFP is something to consider when undergoing the process of applying to graduate school. This is a competitive fellowship that offers financial support for research at the master's and doctorate's levels. You are able to apply once as an undergraduate and once as a graduate student.

[NSF Research Experiences for Undergraduates](https://www.nsf.gov/funding/pgm_summ.jsp?pims_id=5517)

Here you'll find a repository of undergraduate research experiences for students in STEM fields. Psychology, Sociology, and Neuroscience are represented.

[Big Ten Alliance Summer Research Opportunties Program](http://www.btaa.org/resources-for/students/srop/introduction)

This is another repository of undergraduate research experiences. It includes a common application to approximately 10 institutions in the Midwest. This one is open to all disciplines but some institutions may focus more on the life sciences.

**[↥ Back to Top](#lab-resources)**
