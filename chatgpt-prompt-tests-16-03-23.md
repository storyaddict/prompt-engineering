# Testing Specificity of Syntax in ChatGPT Prompts

Focusing on two subjects:

1. Setting up a home media server.
2. Automating current or anticipated workflow routines.

## Home Media Server Experimenation

One useful focus of LLM chatbots is helping you focus thought processes. They are very useful as brainstorming tools. 
I have several media files stored on a laptop hard drive that I would like to be able to access on another machine or stream to my TV. 
I went through a couple of different variations on asking ChatGPT what tools were available to do this.

### Prompt Example 1:

```
I would like to set up a home media server. 
I need to install the necessary software in a desktop OS, not a server OS. 
The OS I'm running is Ubuntu 22.10. 
I need this software to make audio and video files stored locally available on the LAN and accessible to VLC media player. 
I don't want to use Plex, only open-source software.
```

In a previous attempt, ChatGPT had defaulted to recommending Plex. 
Which I didn't want, so I added that I specifically didn't want to use Plex, only open-source software.

Next ChatGPT recommended `minidlna` which was a fine alternative, but if I'm streaming this to my smart TV it would be great if it could also recommend easy GUI tools, or tools that might already have a smart TV app like Jellyfin.

### "Final" Prompt:

```
I would like to set up a home media server. 
I need to install the necessary software in a desktop OS, not a server OS. 
The OS I'm running is Ubuntu 22.10. 
I need this software to make audio and video files stored locally available on the LAN and accessible to VLC media player. 
I don't want to use Plex or Samba, and only want to use open-source software. GUI tools preferred.
```
## Chat GPT Response:

There are several open-source media server options that you can use to set up a home media server on your Ubuntu 22.10 desktop. Here are two options that meet your requirements:

1. Emby Server: Emby is a free and open-source media server that allows you to stream and organize your media files. It has a user-friendly web interface that can be accessed from any device on your local network. Emby supports a wide range of media formats, including video, music, and photos. To install Emby Server on your Ubuntu desktop, you can follow these steps:

   a. Open a terminal window and run the following commands to add the Emby repository and install the server:
    
   ```bash
    sudo apt-get install apt-transport-https
    wget -O - https://github.com/MediaBrowser/Emby.Releases/releases/download/4.7.4.0/emby-server-deb_4.7.4.0_amd64.deb | sudo dpkg -i -
   ```
    
   b. After the installation is complete, start the Emby Server by running the following command:
   
   ```bash
   sudo systemctl start emby-server
   ```
   
   c. You can then access the Emby web interface by opening a web browser and navigating to http://localhost:8096. Follow the setup wizard to configure your media library and start streaming your files.

2. Jellyfin: Jellyfin is another free and open-source media server that allows you to stream and organize your media files. It is a fork of the Emby project and offers similar functionality. Jellyfin also has a user-friendly web interface that can be accessed from any device on your local network. To install Jellyfin on your Ubuntu desktop, you can follow these steps:

   a. Open a terminal window and run the following commands to add the Jellyfin repository and install the server:

    ```bash
    sudo apt-get install apt-transport-https
    wget -O - https://repo.jellyfin.org/ubuntu/jellyfin_team.gpg.key | sudo apt-key add -
    echo "deb [arch=$( dpkg --print-architecture )] https://repo.jellyfin.org/ubuntu $( lsb_release -c -s ) main" | sudo tee /etc/apt/sources.list.d/jellyfin.list
    sudo apt-get update
    sudo apt-get install jellyfin
    ```
   b. After the installation is complete, start the Jellyfin Server by running the following command:
    
    ```bash
    sudo systemctl start jellyfin
    ```
    
It's now giving me two viable options that fit my parameters. I'll need to experiment a bit to see if the instructions are correct since additional configuration will be needed to specify directories, and server behavior, but if I didn't already know that Emby an Jellyfin were available options this would be a great jumping off point.

## Workflow Automation

For this example, I took a much broader approach when starting. 

### Prompt 1:

```
I'm trying to automate my entire workday
```

**NOTE:** Some of the questions I ask it, I may already know the answer to, I just want to see how it responds. I also try to confirm when it does what I want with a "thank you" or "perfect" etc. But correct its misunderstandings too.

### ChatGPT Response 1:

Automating your workday can be a great way to save time and increase productivity. Here are a few steps you can take to get started:

  1.  Identify repetitive tasks: Take a close look at your daily routine and identify any tasks that you perform regularly. These could include sending emails, scheduling meetings, filling out forms, or anything else that you do on a daily or weekly basis.

  2.  Choose automation tools: There are many automation tools available that can help you streamline your workflow. Look for tools that can automate the tasks you identified in step 1. For example, you could use a scheduling tool to automate your calendar, or a chatbot to answer frequently asked questions.

  3.  Create workflows: Once you have chosen your automation tools, create workflows that will automate your repetitive tasks. For example, you could create a workflow that automatically sends a follow-up email after a meeting, or a workflow that automatically fills out a form when it is submitted.

  4. Test your workflows: Before you fully automate your workday, test your workflows to make sure they are working correctly. This will help you identify any issues and refine your workflows.

  5.  Adjust and refine: As you start to automate your workday, you may find that certain tasks require more or less automation. Be prepared to adjust and refine your workflows as needed to ensure that you are getting the most out of your automation tools.

Remember, automation is not a one-time event, but an ongoing process. By continuously refining and optimizing your workflows, you can maximize your productivity and streamline your workday.

### Prompt 2 (Follow Up):

```
Can I automate tasks like clicking parts of a browser?
```

### ChatGPT Response 2:

Yes, you can automate tasks like clicking parts of a browser using browser automation tools like Selenium WebDriver or Puppeteer. These tools allow you to script interactions with a browser, including clicking buttons, filling out forms, and navigating to different pages.

To get started, you will need to download and set up the browser automation tool of your choice. Once you have done this, you can use the tool's scripting capabilities to write code that will automate your tasks. For example, you could write a script that navigates to a specific URL, clicks a button on the page, fills out a form, and submits it.

Keep in mind that browser automation can be complex, and it may take some time to learn how to use these tools effectively. You may also need to write code in a programming language like Python or JavaScript, so some coding knowledge will be required. However, once you have mastered these tools, you can save a lot of time by automating repetitive tasks and freeing up your time for more important work.

### Prompt 3 (Follow Up):

```
Are either of the tools you mentioned open source?
```

**NOTE:** I was wondering if ChatGPT would understand "either of the tools you mentioned" instead of me specifying them by name. 
Assumed best practice would be to name the apps specifically when asking whether they are open source, but ChatGPT correctly interpreted my question.

### ChatGPT Response 3:

Yes, both Selenium WebDriver and Puppeteer are open source browser automation tools.

Selenium WebDriver is an open source tool that allows you to automate interactions with web browsers, including clicking buttons, filling out forms, and navigating between pages. It supports a wide range of programming languages, including Java, Python, C#, and JavaScript, and can be used to automate testing, web scraping, and other tasks.

Puppeteer is another open source tool for browser automation that was developed by Google. It provides a high-level API for automating interactions with the Chrome and Chromium browsers and can be used to perform tasks like taking screenshots, generating PDFs, and scraping data from web pages. Puppeteer is written in Node.js and can be used with JavaScript or TypeScript.

Both Selenium WebDriver and Puppeteer are powerful tools that can save you a lot of time and effort by automating repetitive tasks. However, they do require some technical knowledge to use effectively, so it's important to invest time in learning how to use them before trying to automate complex tasks.

### Prompt 4 (Follow Up):

```
Awesome, thank you. What about automating office software?
```

### ChatGPT Response 4:

Yes, it is possible to automate office software as well. Microsoft Office, for example, provides a powerful automation platform called Visual Basic for Applications (VBA) that allows you to write macros and scripts to automate tasks in Excel, Word, and other Office applications. You can use VBA to automate tasks like generating reports, formatting documents, and analyzing data.

In addition to VBA, there are other tools available for automating office software, such as Python packages like PyWin32 and openpyxl, which can be used to automate tasks in Excel and other Office applications.

There are also third-party tools like UIPath, which is a platform for automating business processes that includes support for automating tasks in Microsoft Office applications.

Automating office software can be a great way to save time and reduce errors, but it does require some technical knowledge and programming skills. However, there are many resources available online to help you learn how to automate tasks in Microsoft Office and other software applications.

### Prompt 5 (Follow Up):

```
Can I integrate a LLM like you into Microsoft word or LibreOffice?
```

### ChatGPT Response 5: 

Yes, it is possible to integrate a language model like me (ChatGPT) into Microsoft Word or LibreOffice to assist with writing and editing documents.

One way to do this is to use an add-in or plugin that integrates with your word processor and provides access to the language model's API. For example, there are plugins available for Microsoft Word that allow you to access OpenAI's GPT-3 API directly from within the Word interface.

Another approach is to use a separate application or website to generate text using the language model, and then copy and paste the text into your word processor. This can be done using the OpenAI API or other language model APIs.

Keep in mind that using a language model for writing and editing documents can be helpful, but it is important to review the output carefully and ensure that it is accurate and appropriate for the context. It's also important to understand the limitations of language models and not rely on them too heavily for critical tasks.

### Prompt 6 (Follow Up):

```
Makes sense. Can you integrate with LibreOffice writer?
```

### ChatGPT Response 6:

**NOTE:** ChatGPT starts to repeat itself here, so I got more specific with my next request.

Yes, it is possible to integrate a language model like me (ChatGPT) with LibreOffice Writer to assist with writing and editing documents.

One way to do this is to use a Python script that utilizes the OpenAI API to generate text using the language model, and then use LibreOffice's built-in Python scripting functionality to insert the generated text into the Writer document. LibreOffice provides a Python API that allows you to automate tasks within Writer, including inserting and formatting text, creating tables, and more.

Another approach is to use a separate application or website to generate text using the language model, and then copy and paste the text into LibreOffice Writer.

Keep in mind that using a language model for writing and editing documents can be helpful, but it is important to review the output carefully and ensure that it is accurate and appropriate for the context. It's also important to understand the limitations of language models and not rely on them too heavily for critical tasks.

### Prompt 7 (Follow Up):

```
I understand, I'll be careful. Please write me a step by step guide on how to integrate chatgpt with LibreOffice Writer.
```

### ChatGPT Response 7:

Sure, here is a step-by-step guide on how to integrate ChatGPT with LibreOffice Writer:

  1.  Install Python: If you don't have Python installed on your computer, download and install the latest version of Python from the official website.

  2.  Install OpenAI API: Install the OpenAI API client library for Python by running the following command in a terminal or command prompt window:

    ```bash
    pip install openai
    ```
  3.  Create an OpenAI API key: If you don't already have an OpenAI API key, create one by following the instructions on the OpenAI website.
  4.  Create a Python script: Create a new Python script that will generate text using the OpenAI API. Here is an example script that generates a response to a given prompt:

    ```python
    import openai
    openai.api_key = "YOUR_API_KEY_HERE"

    def generate_response(prompt):
        response = openai.Completion.create(
            engine="davinci",
            prompt=prompt,
            temperature=0.7,
            max_tokens=1024,
            top_p=1,
            frequency_penalty=0,
            presence_penalty=0
      )
    return response.choices[0].text.strip()
    ```
  Replace "YOUR_API_KEY_HERE" with your actual OpenAI API key.
  5.  Save the script: Save the script to a location on your computer where you can easily find it later.
  6.  Open LibreOffice Writer: Open LibreOffice Writer and create a new document.
  7.  Open the Python IDE: Open the Python IDE that comes with LibreOffice Writer. This can be done by selecting "Tools" > "Macros" > "Edit Macros" from the LibreOffice Writer menu.
  8.  Create a new macro: In the Python IDE, create a new macro by clicking "File" > "New" > "Python Macro" from the menu.
  9.  Add the Python script: In the new macro window, copy and paste the Python script you created earlier into the editor.
  10.  Save the macro: Save the macro with a descriptive name that you will remember, such as "OpenAI_Response".
  11.  Run the macro: Close the macro editor and return to the LibreOffice Writer document. Select "Tools" > "Macros" > "Run Macro" from the menu. In the "Macro Selector" window, select the macro you just created and click "Run".
  12.  Use the macro: In the "Run Macro" window, enter a prompt for the language model to generate a response. The macro will call the Python script, generate a response, and insert it into the document.

  That's it! You have now integrated ChatGPT with LibreOffice Writer and can use it to generate text within your documents. Keep in mind that this is just a basic example, and you can modify the Python script to generate more complex responses or to work with different language models.
  
### Prompt 8 (Follow Up):

```
Please explain the individual parts of your example python script.
```

### ChatGPT Response 8

Sure, here is an explanation of the individual parts of the example Python script I provided earlier:

```python
import openai
openai.api_key = "YOUR_API_KEY_HERE"
```

This imports the OpenAI API client library for Python and sets your API key for authentication. You will need to replace "YOUR_API_KEY_HERE" with your actual OpenAI API key.

```python
def generate_response(prompt):
    response = openai.Completion.create(
        engine="davinci",
        prompt=prompt,
        temperature=0.7,
        max_tokens=1024,
        top_p=1,
        frequency_penalty=0,
        presence_penalty=0
    )
    return response.choices[0].text.strip()
```

This is a function that generates a response to a given prompt using the OpenAI API. Here is a breakdown of the parameters used in the openai.Completion.create function:

- engine: The name of the language model to use. In this case, we are using the "davinci" model, which is one of the most powerful models available from OpenAI.
- prompt: The prompt for the language model to generate a response to. This is the text that you pass into the function when you call it.
- temperature: Controls the randomness of the generated output. Higher values result in more diverse output, while lower values result in more conservative output.
- max_tokens: The maximum number of tokens (words and punctuation marks) to include in the generated output.
- top_p: A value between 0 and 1 that controls the diversity of the generated output. Higher values result in more diverse output, while lower values result in more conservative output.
- frequency_penalty and presence_penalty: Penalty parameters that can be used to discourage repetition of certain words or phrases in the generated output.

The function returns the generated response as a string, with any leading or trailing whitespace removed using the strip() function.

You can modify the function parameters to customize the behavior of the language model, depending on your specific needs and preferences.

I hope this explanation helps! Let me know if you have any other questions.

### Prompt 9 (Follow Up, but New Direction):

```
My automation workflow will probably be focused solely on Ubuntu Linux. What good desktop automation tools are there for Ubuntu?
```

### ChatGPT Response 9:

There are several good desktop automation tools for Ubuntu Linux that you can use to automate your workflow. Here are a few popular ones:

   1.  Selenium: Selenium is a popular open-source tool for automating web browsers. It supports multiple programming languages and can be used to automate repetitive tasks in web applications.

   2.  Autokey: Autokey is a desktop automation utility for Linux and X11. It allows you to create macros, automate repetitive tasks, and perform various other desktop automation tasks.

   3.  Xdotool: Xdotool is a command-line tool that lets you simulate keyboard input and mouse activity on a Linux desktop. It can be used to automate repetitive tasks such as opening applications, switching between windows, and clicking buttons.

   4.  PyAutoGUI: PyAutoGUI is a Python library that allows you to control the mouse and keyboard to automate tasks on the desktop. It can be used to automate repetitive tasks such as filling out forms, clicking buttons, and typing text.

   5.  Robot Framework: Robot Framework is a generic test automation framework that can be used for desktop automation. It provides support for a wide range of applications and operating systems, including Linux.

These tools are just a few examples of the many desktop automation tools available for Ubuntu Linux. Depending on your specific needs and preferences, you may find one or more of these tools to be useful for automating your workflow.

### "Final" Prompt

I tried to create a very specific, multiple step automation prompt to see how ChatGPT responded:

```
Please help me automate this workflow: my day starts at 9am. My Ubuntu OS needs to boot up, and open my Firefox web browser to protonmail, the canonical ubuntu-docs page, and Github. 
I also want VS Code to open, and run a git pull. 
Also open the application "Cider" so I can listen to my Apple Music. 
I want an instant message sent to my boss through Element/Matrix wishing them a good morning, and informing him that I'm at my desk and starting work. 
Ask him what he wants me to prioritize today. 
Based on his response, create a to-do list using the application Super Productivity, and add a check-in reminder on my calendar in Thunderbird.
```

**NOTE:** this proved a bit too much for ChatGPT, and presents an opportunity to impove it's learning models or the prompt. This is also a good place where prompt chains would make more sense than one prompt. Giving ChatGPT more specific instructions for each desired automation will likely produce better results. Further experimentation needed.

### ChatGPT Response:

To automate this workflow, you can create a shell script that will execute these tasks for you. Here are the steps you can follow:

  1.  Open your terminal and create a new file with a .sh extension using the command touch automate_workflow.sh.

  2.  Open the file in your preferred text editor using the command nano automate_workflow.sh.

  3.  Start by adding the shebang line at the beginning of the file #!/bin/bash to indicate that the script should be interpreted by the bash shell.

  4.  Next, you can use the following commands to automate your workflow:

    ```bash
    #!/bin/bash

    # Open Firefox with specified URLs
    firefox --new-tab https://mail.protonmail.com https://help.ubuntu.com/stable/ubuntu-help/index.html https://github.com/

    # Open VS Code and run git pull
    code && cd ~/path/to/repo && git pull

    # Open Cider
    cider

    # Send message to your boss
    element-desktop --message "Good morning! I'm at my desk and starting work. What would you like me to prioritize today?"

    # Create to-do list in Super Productivity
    super-productivity

    # Add check-in reminder in Thunderbird
    thunderbird --calendar
    ```
    
ChatGPT gets close, and is off to a very good start. However, more specificity is needed to execute the tasks related to Element, Super Productivity and Thunderbird.

## Summary

ChatGPT, and LLM in general, are powerful tools that adapt surprisingly well to a variety of phrasing types. ChatGPT is quick to adjust if corrected, or if asked to complete a more specific task.
Prompt engineers will have to use some trial and error in developing their prompt libraries and prompt chains to make sure they are getting the desired results.

## Notes and Future Considerations
All of ChatGPTs scripts and code should be vetted before being put into production.
Software tools it mentions may be outdated if they've updated since 2021 (very likely). Search for the projects independently and adjust version numbers or names accordingly.
The examples in this document have not been vetted or tested in real world environment. They are here for deomonstration purposes only.
