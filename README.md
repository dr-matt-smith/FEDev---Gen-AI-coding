[back to assessments](https://github.com/dr-matt-smith/FEDev---assessment-samples-and-walkthroughs?tab=readme-ov-file) <<<


# FEDev---Gen-AI-coding

These are the steps to follow to work with OpenCode AI and a GitHub Student Developer account
- which should provide free GitHub CoPilot AI credits
  
  - Learn about the free benefits of the **Github Student Developer Pack**
    - https://github.com/education/students

  - Sign up to the **GitHub Student Developer Pack**
    - https://education.github.com/pack
    - you must use your TU Dublin university email address, to get the free student&nbsp;benefits

This assumes you are working on an MS Windows 11 computer
-the steps here are for computers with student accounts (i.e. no administrator privilege)


## Step 0: How to download and install the Celbridge application

Use whatever IDE / code editor you're used to.

One candidate, if you're using Windows 11, is the free, open-source Celbridge workbench application.

To install the latest version of the Windows Celbridge workbench application do the following:

- if this website will open on your computer, you can simply visit https://www.celbridge.org/
  - visit the Download page
  - click the Download button
    - this will  download the Celbridge Microsoft `.msix` installer program
      - a file in the form `Celbridge_A.B.C.0_x64.msix`
  - run the installer to install Celbridge on your computer

![Download button on Celbridge.org site](/images/0_celbridege_download.png)


- however, since celbridge.org is a new website it has not been added to some university approved site lists, so on the university wifi you may get a security warning
  - in which case visit the **Releases** page for the Celbridge GitHub repository at: https://github.com/celbridge-org/celbridge/releases
  - the most recent release will be at the top of this page, click the small arrow to list the **Assets**
  - download and run the Celbridge Microsoft `.msix` installer program
    - a file in the form `Celbridge_A.B.C.0_x64.msix`

![Celbridge installer from GitHub site](/images/0_celbridge_github.png)

At the time of writing the most up-to-date version fo Celbridge was 0.2.4.

## Step 1: Download OpenCode executable

Vist the OpenCode website:
- https://opencode.ai/


![Celbridge installer from GitHub site](/images/1_opencode_website.png)


Install OpenCode on the computer

One way is to:
- Windows
  - open a **Git Bash** terminal 
- maxOS/Linux
  - probably any terminal/shell will be fine :-)
- use the **curl** method shown on the OpenCode page

![open Git Bash](/images/2_gitbash.png)

Note, copy/paste is very fiddly with the Git-Bash terminal - using right-mouse button menu for Copy and Paste...
- CTRL-C / CTRL-V don't seem to work unfortunately ...

```bash
curl -fsSL https://opencode.ai/install | bash
```

![Git Bash CURL](/images/3_curl.png)

![Git Bash CURL](/images/4_install_opencode.png)



This will install an `opencode.exe` executable program in `c:\Users\<yourUsername>\.opencode\bin\opencode.exe`

If your account does not have administrator privilege you'll need to know this path, to run the program
- (since it will not have been added to the System `PATH` environment variables)

![OpenCode install location](/images/6_opencode_exe_location.png)



## Step 2: Open the project you wish to co-code with OpenCode

If you are working with an existing project, then open that project in your editor

If you are working on a new project, then create the new project and open it in your editor.

For example,
- the following screenshots show me cloning the Squid Game project from GitHub, installing the Node libraries with `npm install`, and running the web server with `npm run dev`...

![Squid Game repo](/images/10_squid_game_repo.png)
![Squid Game repo clone](/images/11_git_clone.png)
![Squid Game repo clone](/images/20_celbridege_npm_install.png)
![Squid Game repo clone](/images/21_npm_run_dev.png)



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

![Run OpenCode](/images/30_opencode_connect.png)

Then choose the GitHub CoPilot option.

![OpenCode connect](/images/31_connect_GitHub_Copilot.png)

This will display an 8-digiti special code, and a web link to GitHub

![OpenCode connect code](/images/32_github_connect_code.png)

Click the link and login into your GitHub account.

![OpenCode connect code](/images/40_github_verify_session.png)

Enter the 8-digit code

![OpenCode connect code](/images/41_github_code.png)

Athorise Anomalyco to work with your GitHub resources (if you're happy to do so of course...)

![GitHub authorise](/images/42_authorise_anomalco.png)

![Github all set](/images/43_all_set.png)


## Step 6: Choose your GenAI model

Next choose your GenAI model
- the Claude models are probably the best for co-pilot programming

![OpenCode choose model](/images/44_select_model.png)

## Step 7: Tell OpenCode to record a log of your session to a text file

I recommend you use the following prompt at the beginning of each GenAI session
- so you have a readable transcript of your interactions with OpenCode

```bash
please record a transcript of our interactions in Markdown format in file "session1.md"
```

![OpenCode choose model](/images/50_prompt_for_transcript.png)

![OpenCode choose model](/images/51_transcript_file.png)

You can save subsequence sessions in files `session1.log` and so on... in case you don't get all your work completed in one session...


## Step 8: Choose PLAN or BUILD and work away with OpenCode

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


## Example of OpenCode features added to SvelteKit project

Here I asked Claude to add a separate character page for HoYeonJung...

![OpenCode choose model](/images/48_add_a_new_character_page.png)

![OpenCode choose model](/images/49_character_hoyeonjung_created.png)

## More information

The OpenCode docs:
- https://opencode.ai/docs

Matt's screencast of using OpenCode to add features to a SvelteKit project
- https://go.screenpal.com/watch/cOnqF5n0aTr






