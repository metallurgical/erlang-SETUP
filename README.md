[logo_main]: https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcST9v8A3x54BSoD9ipEB2i_QLTkh7OCY6VK_sGI_THbAH2IY0G1 "Logo Title Text 1"
[logo_sub]: https://www.cannastaff.com/include/themes/nasthon1001-restyle/images/delicious.gif "Logo Title Text 2"

![alt text][logo_main]  Erlang Inital Setup
------------
Configurations Setting for ERLANG to work with both linux and windows. Requirements Need :
  - YAWS web server
  - ERLANG
  - relab

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
  - Coming..

![alt text][logo_main]  Yaws Installation
-----------
- **( Windows)**
  - Download it from here http://yaws.hyber.org/download/ or http://yaws.hyber.org/download/Yaws-2.0.2-windows-installer.exe (Choose based on your pc's specification)
  - Install as ussual
  - After finish, need to setup environemt `path` for `yams` command to work in CLI.
    - Ussually the yams's bin path automatically added into path environment variable. If not, copy the bin's path, mine is : `C:\Program Files (x86)\Yaws-2.0.2\bin;` at the time of writing
  -Finish, Now you can start the yams's server by typing :
    - `yams -i`
    - You should see the message from the CLI that the yam's server is running on port ****. 
    - Open it from the browser and should see the yams's page with example.
- **( Linux )**
  - Coming...
