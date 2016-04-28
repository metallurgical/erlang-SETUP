[logo_main]: https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcST9v8A3x54BSoD9ipEB2i_QLTkh7OCY6VK_sGI_THbAH2IY0G1 "Logo Title Text 1"
[logo_sub]: https://www.cannastaff.com/include/themes/nasthon1001-restyle/images/delicious.gif "Logo Title Text 2"

![alt text][logo_main]  Erlang Inital Setup
------------
Configurations Setting for ERLANG to work with both linux and windows. Requirements Need :
  - YAWS web server(optional)
  - MOCHIWEB Web Server(optional - easy to setup)
  - ERLANG
  - rebar(erlang compiler)
  - cygwin(unix-like environment for windows)
  - Kerl( easy tools to handle otp/erlang installation - mainly for linux )

![alt text][logo_main]  Cygwin Installation( Windows User )
-----------
A large collection of GNU and Open Source tools which provide functionality similar to a Linux distribution on Windows.
A DLL (cygwin1.dll) which provides substantial POSIX API functionality. After install this, you can use linux command on windows by using cygwin bash CLI.
- Download the installer here : https://www.cygwin.com/install.html , choose either 32bit or 64bit depend on your cpu bit.
- Install the installer, and after finish installation, windows should popup which give you permission to choose the library to download. As cygwin not install all the package and DO NOT INSTALL ALL THE PACKAGE(because there is a package that we dont use). For safety, just leave the installer to choose default option to install.
- DONE!
- You can also intall the package directly from the cygwin bash like linux terminal. To enable this follow further step :
  - Install `apt-cyg` first
    - `lynx -source rawgit.com/transcode-open/apt-cyg/master/apt-cyg > apt-cyg`
    - `install apt-cyg /bin`
  - After that you'll be able to install say the package "lynx" including dependencies by running:
    - `apt-cyg install lynx`
    - or `apt-cyg install make`

![alt text][logo_main]  Erlang Installation
-----------
- **( Windows )**
  - Download it from here https://www.erlang.org/downloads or http://erlang.org/download/otp_win64_18.3.exe (Choose based on your pc's specification)
  - Install as ussual
  - After finish, need to setup environemt `path` for `erl` command to work in CLI. 
  - Go to environment variable setup at windows properties
    - Go to installation `erlang folder dir` on program files(location used to install erlang/opt), and copy the full `bin` path, mine is : `C:\Program Files\erl7.3\bin` at the time of writing
    - Go to system variables on system properties(you know that), find variable `path` at `System Variables's` section.
    - At the variable path, there must be existing others path available there, we need to append it by separating it with `;`
    - Append those variable with the copied path. Should be : `....;C:\Program Files\erl7.3\bin;`
  - Finish install. Now the `erl` or `werl` command should be avalaible inside CLI.
- **( Linux )**
  - run `sudo apt-get install erlang`
  - Done!

![alt text][logo_main]  Mochiweb Installation(Skip if not related)
-----------
Mochiweb is a lightweight http web server created to run erlang code as easy as possible. To run our application. First we need to install Mochiweb and create our application using Mochiweb Built-In command for creating new project.
- **( Windows)**
  - Open `cygwin` bash terminal
  - In our example, go to main container place for our application. Mine is : `C:/erlang`.
  - Cloning mochiweb repo from github
    - `git clone git://github.com/mochi/mochiweb.git`
  - After finish cloning, enter into directory : `cd mochiweb`
  - (IMPORTANT) Create our application there by using this command :
    - `make app PROJECT=cobaan`
    - `make` command in default does not available on cygwin package, to enable this, we need to download the `make` package
      - See **CYGWIN** installation step above, go to package installation part. After install `apt-cyg` command, we can install `make` package nby typing : `apt-cyg install make`. 
      - DONE!
      - Then, re-type `make app PROJECT=cobaan` again(skip if already passed and successfull)
    - Mochiweb will create `cobaan` application **outside** the folder mochiweb, not the **inside**.
  - Go into newly created application : `cd ..(jump out into parent dir)` and followed by `cd cobaan(project name)`
  - Compile the new application : `make`
  - And finally run the server by running the shell script: `./start-dev.sh`, after execute, you can see a bunch of report message indicate that the application are running.
  - And now, you can open the browser and type `localhost:8080` from the url and see the successfull message there. As default, mochiweb will run the server on `port 8080`
- **( Linux )**
  - In our example, go to main container place for our application. Mine is : `/home/metallurgical/Documents/erlang`.
  - Cloning mochiweb repo from github
    - `git clone git://github.com/mochi/mochiweb.git`
  - After finish cloning, enter into directory : `cd mochiweb`
  - (IMPORTANT) Create our application there by using this command :
    - `make app PROJECT=cobaan`
    - Mochiweb will create cobaan application **outside** the folder mochiweb, not the **inside**.
  - Go into newly created application : `cd ..(jump out into parent dir)` and followed by `cd cobaan(project name)`
  - Compile the new application : `make`
  - And finally run the server by running the shell script: `./start-dev.sh`, after execute, you can see a bunch of report message indicate that the application are running.
  - And now, you can open the browser and type `localhost:8080` from the url and see the successfull message there. As default, mochiweb will run the server on `port 8080`

- **References**
  - Installation `apt-cyg` : http://superuser.com/a/41139
  - Mochiweb repo : https://github.com/mochi/mochiweb

  

![alt text][logo_main]  Yaws Installation( Skip if not related )
-----------
- **( Windows)**
  - Download it from here http://yaws.hyber.org/download/ or http://yaws.hyber.org/download/Yaws-2.0.2-windows-installer.exe (Choose based on your pc's specification)
  - Install as ussual
  - After finish, need to setup environemt `path` for `yams` command to work in CLI.
    - Ussually the yams's bin path automatically added into path environment variable. If not, copy the bin's path, mine is : `C:\Program Files (x86)\Yaws-2.0.2\bin;` at the time of writing
  - Finish, Now you can start the `yams's` server by typing :
    - `yams -i`
    - You should see the message from the CLI that the `yam's server is running on port ****`
    - Open it from the browser and should see the yams's page with example.
- **( Linux )**
  - Coming...

![alt text][logo_main]  Rebar Installation
-----------
Rebar is an Erlang build tool that makes it easy to compile and test Erlang applications, port drivers and releases. rebar is a self-contained Erlang script, so it's easy to distribute or even embed directly in a project. Where possible, rebar uses standard Erlang/OTP conventions for project structures, thus minimizing the amount of build configuration work. rebar also provides dependency management, enabling application writers to easily re-use common libraries from a variety of locations (git, hg, etc).
- **( Windows )**
  - Cloning rebar repo into specified directory. Must be note that, rebar is standalone code, so, you can install it anywhere as later we will add rebar's path into windows environment path variable. 
  - Open `cygwin` bash : git clone git://github.com/rebar/rebar.git ( i clone this on C:  drive )
  - After the cloning, rebar folder should be created. cd into that folder : `cd rebar`
  - And compile the code : `./bootstrap` (should have bootstrap.bat file on rebar folder)
  - After execute above command, you should able to see the compile message from the terminal and if successfull should see this message :
    - `Congratulations! You now have a self-contained script called "rebar" in your current working directory. Place this script anywhere in your path and you can use rebar to build OTP-compliant apps.`
  - After finish compile, you can see the `rebar.cmd` file was created. 
  - To enable `rebar` command works on CMD or cygwin bash, we must add the rebar path into windows environment variable path.
  - Go to system variable on windows, find the `path` variable under system variable section, and append this path, mine is : `....;C:\rebar\rebar;`
  - Choose ok and done.
  - After this, rebar command should available on CLI.
  - DONE
- **( Linux )**
  - coming....
- **References**
  - Rebar repo : https://github.com/basho/rebar
  
![alt text][logo_main]  Kerl Installation
-----------
- **( Windows )**
  - coming...
- **( Linux )**
  - Open terminal `ctrl + alt + t`
  - Download script directly from github : `curl -O https://raw.githubusercontent.com/kerl/kerl/master/kerl`
  - And make it executable : `chmod a+x kerl`
  - And drop it into the PATH to ensure the `kerl` command is global by :
    - 1st option : copy the `kerl`'s executable file from dir that we download it, and cut those file and paste into : `/usr/local/bin`
    - 2nd option by using terminal : `export PATH=$PATH:/path/where/the/file/is/download/name_of_file_we_downloaded`
  - Done, this should be make the `kerl` command is available from any path where you located.
  - Now we can manage/install/activate/deactivate/list the erlang/otp build anytime.
- **References**
  - kerl : https://github.com/kerl/kerl
  

![alt text][logo_main]  Erlang Installation using kerl
-----------
- **( Windows )**
  - coming...
- **( Linux )**
  - Before we install erlang build, here is a a command to list the available releases
    - `kerl list releases`, output :
    - `Getting the available releases from erlang.org...
       R10B-0 R10B-10 R10B-1a R10B-2 R10B-3 R10B-4 R10B-5 R10B-6 R10B-7 R10B-8 R10B-9 R11B-0 R11B-1 R11B-2 R11B-3 R11B-4 R11B-5 R12B-0 R12B-1 R12B-2 R12B-3 R12B-4 R12B-5 R13A R13B01 R13B02-1 R13B02 R13B03 R13B04 R13B R14A R14B01 R14B02 R14B03 R14B04 R14B_erts-5.8.1.1 R14B R15B01 R15B02 R15B02_with_MSVCR100_installer_fix R15B03-1 R15B03 R15B R16A_RELEASE_CANDIDATE R16B01 R16B02 R16B03-1 R16B03 R16B 17.0-rc1 17.0-rc2 17.0 17.1 17.3 17.4 17.5 18.0 18.1 18.2.1 18.2 18.3
       Run "./kerl update releases" to update this list from erlang.org`
  - Then pick which build to install : `kerl build 17.0 17.0` --> kerl build <release> <build_name>
