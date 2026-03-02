[back to assessments](https://github.com/dr-matt-smith/FEDev---assessment-samples-and-walkthroughs?tab=readme-ov-file) <<< 


# FEDev---Gen-AI-coding

These are the steps to follow to work with OpenCode AI and a GitHub Student Developer account
- which should provide free GitHub CoPilot AI credits

This assumes you are working on an MS Windows 11 computer
-the steps here are for computers with student accounts (i.e. no administrator privilege)


## Step 0: How to download and install the Celbridge application

To install the latest version of the Windows Celbridge workbench application do the following:

- if this website will open on your computer, you can simply visit https://www.celbridge.org/
  - visit the Download page
  - click the Download button
    - this will  download the Celbridge Microsoft `.msix` installer program
      - a file in the form `Celbridge_A.B.C.0_x64.msix`
  - run the installer to install Celbridge on your computer


- however, since celbridge.org is a new website it has not been added to some university approved site lists, so on the university wifi you may get a security warning
  - in which case visit the **Releases** page for the Celbridge GitHub repository at: https://github.com/celbridge-org/celbridge/releases
  - the most recent release will be at the top of this page, click the small arrow to list the **Assets**
  - download and run the Celbridge Microsoft `.msix` installer program
    - a file in the form `Celbridge_A.B.C.0_x64.msix`

## Step 1: Download OpenCode executable

Vist the OpenCode website:
- https://opencode.ai/

Install OpenCode on the computer

One way is to:
- open a Git Bash terminal
- use the "curl" method shown on the OpenCode page

```bash
curl -fsSL https://opencode.ai/install | bash
```

This will install an `opencode.exe` executable program in `c:\Users\<yourUsername>\.opencode\bin\opencode.exe`

If your account does not have administrator privilege you'll need to know this path, to run the program
- (since it will not have been added to the System `PATH` environment variables)


At the time of writing the most up-to-date version fo Celbridge was 0.2.4.

## Step 2: Open the project you wish to co-code with OpenCode

If you are working with an existing project, then open that project in your editor

If you are working on a new project, then create the new project and open it in your editor.

## Step 3: Open a command line console in your project directory

If working with an editor offering a Console (such as Celbridge, VS Code, Jetbrains WebStorm), then open a command line console
- do a `dir` to check your console is looking at the directory for your project

If your editor does not offer a built-in terminal/console, then:
  - start a new CMD terminal process
  - then 'cd' into your project directory

It's important the console that you run OpenCode in is looking at your project directory
- so OpenCode can find your project files 

## Step 4: Run OpenCode and connect to your GitHub CoPilot account

If you installed OpenCode with admin rights, you should simply be able to type `opencode` at the command line
- or `!opencode` if using the Python Console in Celbridge

However, if you didn't have admin rioghts (e.g. using a university PC) then to run OpenCode you'll need to give it the path to the installed `opencode.exe` executable file:
- `c:\Users\<yourUsername>\.opencode\bin\opencode.exe`

One way to do this is to type out the whole path (inserting your Windows username as appropriate)

Another way to do this is to write a relative path, from your project direcotry to the OpenCode location
- e.g. if you are working in a project `practical2` in your `Downloads` folder, you could type:
  - `..\..\.opencode\bin\opencode.exe`
  - since you need to move out of project folder, then out of the `Downloads` folder, then into the `.opencode\bin` folder

## Step 5: Connect to your GitHub CoPilot Pro resources

Once runing OpenCode, you need to **connect** to your agent provider. Type:
- `/connect`

Then choose the GitHub CoPilot option

This will display an 8-digiti special code, and a web link to GitHub

Log into your GitHub account, enter the 8-digit code, and authorise XX to work with your Github resources.

## Step 6: Choose your GenAI model

Next choose your GenAI model
- the Claude models are probably the best for co-pilot programming

## Step 7: Tell OpenCode to record a log of your session to a text file

It's useful to have a record of your interactive session when GenAI coding. So use a prompt such as the following to get OpenCode to record everything as a text file:
- `please record this session into a text file named "session1.log"`

You can save subsequence sessions in files `session1.log` and so on... in case you don't get all your work completed in one session...


## Step 7: Choose Plan or Build and work away with OpenCode

Work away in OpenCode.

Some useful keyboard shortcuts:

- the `TAB` key
  - switch between PLAN (tell me, but don't change anything) and BUILD (edit my project code) modes.

- summary / detail mode:
  - `CTRL-X` + RIGHT arrow key = detail mode
    - see everything the agent is doing - LOTS of details
  - `CTRL-X` + LEFT arrow key = summary mode - sumamry information for you to read 
    - I work in summary mode most of the time

- `CTRL-P` get a list of comments

- `ESC`
  - exit 


## More information

The OpenCode docs:
- https://opencode.ai/docs

Matt's screencast of using OpenCode to add features to a SvelteKit project
- https://go.screenpal.com/watch/cOnqF5n0aTr






