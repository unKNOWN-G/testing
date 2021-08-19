# <a id="title" >Automate</a>
<font size="4">A</font>utomate is a Python package that automates sending emails, Whatsapp text, images, videos, and audio messages along with other functionalities like creating a group and spam bot.

**Libraries Used**: Selenium, gTTS 
\
&nbsp;
***
## <a id="features" style="color:gren;">Main Features</a>
1) <div style="background-color:#ACDDDE"><b>&nbsp;&nbsp;Bolding</b> Functionality in Emails</div>
   
   * Specific Parts of an Email can now be bolded using `Automate`.
2) <div style="background-color:#CAF1DE"><b>&nbsp;&nbsp;Spam Bot</b> in Whatsapp</div>

    * Using `Automate`, we can send a message multiple times (spam) to a user(s).
3)  <div style="background-color:#EDDFBF"> <b>&nbsp;&nbsp;Audio Sender</b> in Whatsapp</div>  

    * Text messages can now be sent as voice clip using `Automate`
4) <div style="background-color:#CAF1DE"><b>&nbsp;&nbsp;Automate sending all types of media in Whatsapp</b> in Whatsapp</div>

    * Using `Automate`, we can automate sending Text, Images, Videos, Documents, and Audio Clips.
5) <div style="background-color:#FFE9EE"><b>&nbsp;&nbsp;Group Creator</b>  in Whatsapp</div> 
 
    * Process of creating a group and adding participants, and sending invites is automated by `Automate`


&nbsp;
***
## <a id="contents" >Table of Contents</a>
- [Package-name](#title)
- [Main Features](#features)
- [Table of Contents](#contents)
- [Prerequisites](#pre)
- [Installation](#install)
- [What Classes are present in this Library?](#what)
- [Email Class](#email)
    - [Description](#email-desc)
    - [What Methods Do we have?](#email-what)
    - [Importing and assigning Email class](#email-import)
    - [Methods](#email-method)
- [Whatsapp Class](#whatsapp)
    - [Description](#whatsapp-desc)
    - [What Methods Do we have?](#whatsapp-what)
    - [Importing and assigning Email class](#whatsapp-import)
    - [Methods](#whatsapp-method)

***
## <a id="pre" >Prequesites</a>
- Selenium
    ```
     pip install selenium
     ```
- gTTs
    ```
    pip install gtts
    ```
***
## <a id="install" >Installation</a>
- Using PIP
    ```
    pip install automate 
    ```
- Using Conda
    ```
    conda install automate
    ```



***
## <a id="what">What Classes are present in this Library?</a>
- [Email](#email)
- [Whatsapp](#whatsapp)
## <a id="email" >Email Class</a>

### <a id="email-desc" >1.  Description  </a>

This Class Automates the process of sending E-mails to multiple recipients. 
Using the sender_mail and sender_password credentials as input along with mail_subject and mail_body as input, Mails can be sent to numerous recipients individually.

There's an additional functionality of Bolding the content in the body. This feature can be used by alternatively giving the texts in the mail_body list with normal and bold texts [ "Normal text1", "Bold Text 1", "Normal text 2", "Bold Text 2" ....]
>**Note:**
>- To input Multiple lines of string, use triple quotes.                                             
>- It is advised to use organization-specific sender_email that (or) gmails that arent created on this device to avoid security issues with google verification.  
      

### <a id="email-what">2. What Methods Do we have?</a>
- Email Class
    - [send_mails](#mails)

### <a id="email-import">3. Importing and assigning Email class</a>
- Importing the `Email` Class  
    
    ```
    from automate import Email
    ```
- Assign `Email` Class to a Class Variable:
    \
    The Email Sender Class takes inputs as `sender_email`, `sender_password`, `mail_subject`, `mail_body`

    >The Bolding Functionality can be use in body of the Email by alternatingly giving the texts in `mail_body` variable as shown below.  
    >[ "Normal text1", "Bold Text 1", "Normal text 2", "Bold Text 2" ....]

    *Input Parameters*:

    >`sender_email`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: str, Mail ID of the sender
    \
    >`sender_password`&nbsp;: str, Password of the sender
    \
    >`mail_subject`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: str, Subject of the Email 
    \
    >`mail_body`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: list, List of Stings given alternatively with Normal and bolding texts.
    ```
    var = Email(sender_email: "", sender_password: "", mail_subject: "", mail_body: ["",""])
    ```
### <a id="email-method">4. Methods  </a>
- #### <a id="mails">send_mails</a>

    This method Automatically send emails to the recipients.   
    Mails can be sent to multiple recipients also individually by adding their names in the `emails` list.

    *Input Parameters:*  

    >`driver_path`: str, Chrome Driver Address.
    \
    >`emails`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: list, List of Emails to which emails are to be sent.  

    ```
    var.send_mails(driver_path: "", emails: ["",""]) 
    ```  
******

## <a id="whatsapp" >Whatsapp Class</a>
### <a id="whatsapp-desc">1. Description</a>


### <a id="whatsapp-what">2. What Methods Do we have?</a>
- Whatsapp Class
    - [spam_bot](#spam)
        \
    &nbsp;
    - [send_text](#text)
    - [send_image](#image)
    - [send_document](#document)
    - [send_audio](#audio)
    - [create_group](#groupmaker)
        \
    &nbsp;
    - [whatsapp_closer](#closer)
\
&nbsp;
### <a id="whatsapp-import">3. Importing and assigning Email class</a>
- Importing the Whatsapp Class
    ```
    from automate import Whatsapp
    ``` 
- Assign `Whatsapp` Class to a variable

    To initialize the the chrome driver and to login got whatsapp. The usage_data_directory is used to store the QR code information to avoid multiple scanning.   

    *Input Parameters :*  

    >`driver_address` &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; : str, Address of Chrome Driver.  
    >`usage_data_directory` : str, Stores data to help logging multiple times seamless by passing QR code.

    *Code*:
    ```
    var = Whatsapp(driver_address:"", usage_data_directory: "")
    ```

### <a id="whatsapp-method">4. Methods</a>
- #### <a id="spam">spam_bot</a>
    - This method is used to send repeated texts (Spam) to the same person.
    - Messages can be sent to multiple recipients also by the contact names in `name` list.  

    *Input Parameteres :*  
    > `name` &nbsp;: list, Names of the person to whom these messages are to be sent.     
    > `msg` &nbsp;&nbsp;&nbsp;: str, Message.  
        >`count` : int, Number of Messages.

    *Code :*

    ```
    var.spam_bot(name: ["",""], msg: "", count:)
    ```


- #### <a id="text">send_text</a>
    - This method is used to Automatically send messages to the recipient.  
    - ***Multiple messages*** can be sent by adding messages into the `msg` list.  
    - The same set of images, videos can be even sent to ***Multiple people*** by adding names into the `name` list.  

    *Input Parameteres :*   
    >`name`&nbsp;&nbsp;&nbsp;&nbsp;: list, List of all contacts to which it should be send in string format.  
    >`msg` &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: str, Message to be sent.   
    >`select` : bool, Confirm if a particular command should be there on not. It has a Default Value true  

    *Code :* 
    ```
    var.send_text(name: ["",""], msg: "")
    ```
- #### <a id="image">send_image</a>  
    - This method is used to Automatically send image or video to the recipient. 
    - ***Multiple Images, Videos*** can be sent by adding the file address with extension in the `file_address` list. 
    - The same set of images, videos can be even sent to ***Multiple people*** by adding names into the `name` list.  
    - Accepts all formats of image and videos.  

    *Input Parameteres :*   
    >`name`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: list, List of all contacts to which it should be send in string format.  
    >`files_address`&nbsp;: list, Contains strings of address of files to be sent stored in list.   
   >`select` &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: bool, Confirm if a particular command should be there on not. It has a Default Value true  

    *Code :*
    ```
    var.send_image(name: ["", ""], files_address: ["",""], select: bool = True)
    ```

            
- #### <a id="document">send_document</a>  
    - This method is used to Automatically send files as documents to the recipient.
    - ***Multiple Documents*** can also be sent to the recipient by adding the files address in `file_address` list.
    - This same set of documents can be even sent to ***Multiple people*** by adding names into the `name` list.
    - Accepts all formats. 

    *Input Parameteres :*   
    >`name`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: list, List of all contacts to which document should be sent.  
    >`files_address`&nbsp;: list, Contains strings of address of files to be sent stored in list.   
    >`select` &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: bool, Confirm if a particular command should be there on not. It has a Default Value of true  

    *Code :*
    ```
    var.send_image(name: ["", ""], files_address: ["",""], select: bool = True)
    ```

- #### <a id="audio">send_audio </a> 
    - This method converts the given message into a audio recording and send to the recipient.
    - The audio file can be sent to multiple recipients by adding recipients into `name` list.  

    *Input Parameters:*  
    >`name`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: list, List of all contacts to which it should be send in string format.  
    >`msg`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: str, Stores the message in string format.  
   >`file_name`&nbsp;: list, Name of the Audio File.  
    >`file_dir`&nbsp;&nbsp;&nbsp;: str, name of file directory.   
    >`select`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;: bool, Confirm if a particular command should be there on not. It has a Default Value of true    


    *Code :*
    ```
    var.send_audio(name: ["", ""], files_address: ["",""])
    ```     
     
- #### <a id="groupmaker">create_group </a>
    - This method is used to create a whatsapp group.
    - Using the contact names given in `group_list` and group name in `group_name` the whatsapp group is made. 
     
    *Input Parameters:*  
    >`group_list` : list, Stores the list of names(str) to be added in group in a list.  
    >`group_name` : str, Name of the group.  
    >`text_dir`&nbsp;&nbsp;&nbsp;&nbsp;: str, This is an alternate way of giving the list of group members and the group name by storing in a .txt file. Each line in the text file denoteds one contact name and teh name at the end of text file denote Group name. Default filename is take as `group_name.txt` in the project directory



    *Code :*
    ```
    var.create_group(group_list: ["",""], group_name: "", text_dir: str = './group_names.txt')
    ```     
- #### <a id="closer">whatsapp_closer</a>  
    - This method is used to close the running chrome driver.

    *Input Parameters:*  None

    *Code :*
    ```
    var.whatsapp_closer()
    ```
***
## License
### [**MIT**]()

### <div align="center"><font size="5">Made with 💖 from unKNOWN-G</font></div>
