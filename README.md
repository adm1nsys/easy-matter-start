<h1>EASY MATTER START</h1>
<h3>Tutorials for boards:</h3>
<ul>
  <li><a href="#esp">ESP32 C6 Xiao</a></li>
  <li><a href="#">nRF54L15-DK</a></li>
</ul>
<h1>About repo</h1>
<p><b>EN: </b>
I believe that the entry barrier to Matter is quite high — the official documentation is fragmented, and most examples are far from practical use.  
That’s exactly why I decided to create this repository.
</p>

<p>
I truly enjoy working with the Matter protocol, especially <strong>Matter Over Thread</strong>, as it integrates seamlessly with HomeKit and provides much better stability compared to many Wi-Fi-based solutions.
</p>

<p>
When I started working with the <strong>ESP32C6 XIAO</strong>, it became clear that Espressif’s official examples were poorly designed: confusing architecture, unclear event handling, and weak code organization.  
These projects might compile, but they are not suitable as a reliable foundation.  
So I completely <strong>redesigned the project structure from scratch</strong> in Arduino IDE — focusing on clean logic, stability, and transparent Matter event control.  
This repository contains that reworked version — a complete and understandable example of a <em>Matter Over Wi-Fi occupancy sensor</em> with multiple endpoints.
</p>

<p>
As for the <strong>nRF54L15</strong> — the situation is different.  
This is probably <strong>the best hardware</strong> I’ve ever worked with: excellent documentation, clear SDK structure, and well-designed examples.  
However, <strong>as of October 2025</strong>, I could not find a single truly step-by-step tutorial that guides users from creating a project to a fully functional Matter Over Thread device based on the nRF54L15-DK.  
The official Nordic materials contain everything you need, but the information is scattered across different sections, making it hard for beginners to connect all the dots.  
In this repository, I’ve tried to build exactly that kind of path — <em>a clear, sequential, step-by-step guide from zero to adding the device to your smart home</em>.
</p>

<p>
My goal is to create an understandable and reproducible guide that lowers the entry barrier to Matter development — for both ESP users and those working with Nordic hardware.
</p>

<p><b>UA:</b>
Я вважаю, що поріг входу в Matter досить високий — офіційна документація фрагментована, а більшість прикладів далекі від практичного використання.  
Саме тому я вирішив створити цей репозиторій.
</p>

<p>
Мені справді подобається протокол Matter, особливо <strong>Matter Over Thread</strong>, адже він чудово інтегрується з HomeKit і забезпечує значно кращу стабільність порівняно з багатьма рішеннями на Wi-Fi.
</p>

<p>
Коли я почав працювати з <strong>ESP32C6 XIAO</strong>, стало очевидно, що офіційні приклади Espressif зроблені невдало: заплутана архітектура, неочевидна логіка подій і слабка структура коду.  
Такі проєкти можуть скомпілюватися, але їх неможливо використовувати як надійну основу.  
Тому я повністю <strong>переробив структуру проєкту з нуля</strong> в Arduino IDE — з акцентом на зрозумілу логіку, стабільність і прозоре керування подіями Matter.  
У цьому репозиторії знаходиться саме ця оновлена версія — повноцінний та зрозумілий приклад <em>Matter Over Wi-Fi датчика руху</em> з кількома кінцевими точками (Endpoint).
</p>

<p>
Щодо <strong>nRF54L15</strong> — ситуація інша.  
Це, мабуть, <strong>найкраще апаратне забезпечення</strong>, з яким я коли-небудь працював: чудова документація, зрозуміла структура SDK і якісні приклади.  
Проте <strong>станом на жовтень 2025 року</strong> я не знайшов жодного дійсно покрокового посібника, який би проводив користувача від створення проєкту до повноцінного пристрою Matter Over Thread на базі nRF54L15-DK.  
Офіційні матеріали Nordic містять усю потрібну інформацію, але вона розкидана по різних розділах, і новачкам складно скласти все це докупи.  
У цьому репозиторії я намагався побудувати саме такий шлях — <em>чіткий, послідовний та покроковий — від нуля до додавання пристрою в розумний дім</em>.
</p>

<p>
Моя мета — створити зрозумілий і відтворюваний посібник, який знизить поріг входу в розробку Matter — як для користувачів ESP, так і для тих, хто працює з обладнанням Nordic.
</p>

<h3>ESP32C6 Xiao</h3>
<ol>
  <li><a href="#">About board</a><br>
  Pinout, Link on official documentation, little information.
  </li>
  <li><a href="#">Quick Start</a><br>
  Download Arduino IDE, Setup IDE, Download my Constructor-Example (Matter Project)
  </li>
  <li><a href="#">Setup and Start</a><br>
  Setup Project Code including custom events, Add to Home.
  </li>
</ol>
<h3>nRf54L15-DK</h3>
<ol>
  <li><a href="#">Setup workspase</a><br>
  Download VS Code, NCS for VS Code
  <li><a href="#">Start Guide</a><br>
  Coppy NCS Example, build issues (Windows only), flash board, add to home.
  <li><a href="#">ZAP Guide</a><br>
  Download, Open configurations, issues, generate.
  <li><a href="#">How Matter EP works</a><br>
  How to correctly add now EP to don't have problems.
  <li><a href="#">How to make custom IDS</a><br>
  Custom Manufacturer, Serial Numbers, Model.
</ol>
<h3>Other</h3>
<ul>
  <li><a href="#">Documentations</a></li>
  <li><a href="#">Git Repos</a></li>
  <li><a href="#">Links Download</a></li>
</ul>

<h1 id="esp">ESP32C6 Xiao</h1>
<h2>About board</h2>
<h3>Pinout:</h3>
<img src="https://wdcdn.qpic.cn/MTY4ODg1Nzc0ODUwMjM3NA_318648_dMoXitoaQiq2N3-a_1711678067?w=1486&h=1228" alt="esp32c6 xiao pinout" width="500">
<a href="https://wiki.seeedstudio.com/xiao_esp32c6_getting_started/">Get Started with Seed Studio XIAO ESP32C6 official documintation</a>
<p><b>EN:</b>
The above link leads to the official documentation describing how to start working with this board.  
You only need the ability to flash it — no extra tools required.  
This board is a <strong>good and affordable choice</strong> for beginners, but it should not be considered suitable for long-term or industrial IoT solutions.
</p>

<p>
Based on my own experience, both the hardware quality and software libraries provided by Espressif often require deep debugging and architectural fixes.  
I have reworked large parts of their original project to achieve stable Matter Over Wi-Fi operation.
</p>

<p>
As of <strong>October 2025</strong>, Espressif <strong>has not implemented full Matter Over Thread support</strong>.  
While the Thread CLI itself can be launched on this chip, <strong>Matter Over Thread does not actually run</strong> — only Matter Over Wi-Fi is supported.  
Unfortunately, the company’s documentation and marketing materials can be misleading on this point.
</p>

<p>
I also cannot confirm whether Espressif’s Matter stack uses WPA2 or WPA3 for network security.  
Given this uncertainty, relying on Matter Over Wi-Fi for the long term may not be the most future-proof approach as Wi-Fi security protocols continue to evolve.
</p>

<p>
In summary, <strong>ESP32-C6 XIAO is great for experimentation and prototyping</strong>, but it has clear limitations that must be considered when building reliable 24/7 IoT systems.
</p>

<p><b>UA:</b>
Посилання вище веде на офіційну документацію, де описано, як розпочати роботу з цією платою.  
Для старту потрібно лише мати можливість її прошити — жодних додаткових інструментів не потрібно.
</p>

<p>
Це <strong>гарний і недорогий вибір</strong> для початківців, проте цю плату не варто розглядати як рішення для довготривалих або промислових IoT-проєктів.  
З власного досвіду: якість апаратної частини та бібліотек Espressif залишає бажати кращого — для стабільної роботи Matter Over Wi-Fi довелося суттєво переробити оригінальний код.
</p>

<p>
Станом на <strong>жовтень 2025 року</strong> Espressif <strong>не реалізували повну підтримку Matter Over Thread</strong>.  
Хоча <em>Thread CLI</em> на цій платформі запускається, <strong>Matter Over Thread фактично не працює</strong> — лише Matter Over Wi-Fi.  
На жаль, офіційні матеріали компанії можуть вводити користувачів в оману щодо цього.
</p>

<p>
Також немає чіткої інформації, який саме протокол безпеки Wi-Fi використовується в реалізації Espressif — WPA2 чи WPA3.  
Через цю невизначеність Matter Over Wi-Fi навряд чи можна вважати довготривалим рішенням, адже стандарти безпеки Wi-Fi постійно змінюються.
</p>

<p>
Підсумовуючи: <strong>ESP32-C6 XIAO чудово підходить для експериментів та DIY-проєктів</strong>, але має обмеження, які потрібно враховувати при створенні стабільних систем, що працюють 24/7.
</p>

<h2>Quick Start</h2>
Download <a href="https://www.arduino.cc/en/software/">Arduino IDE for MAC/Linux/Windows10/11</a> <b>NOT</b> Arduino App Lab.<br>
<h3>Setup IDE</h3>

<ol>
  <li>Open Arduino IDE</li>
  <li>Open Preferences (Above)</li>
  <li>Add in board manager URL - URL of board and click OK
      
    https://espressif.github.io/arduino-esp32/package_esp32_index.json
  <img src="https://files.seeedstudio.com/wiki/SeeedStudio-XIAO-ESP32C6/img/boards_url.png" alt="menu" width="500">
  </li>
  <li>Download the XIAO ESP32C6 board package.<br>
  <img src="https://files.seeedstudio.com/wiki/SeeedStudio-XIAO-ESP32C6/img/install_board.png" alt="board package" width="500"></li>
  <li>Choose your board as a target (above)<br>
  <img src="https://files.seeedstudio.com/wiki/SeeedStudio-XIAO-ESP32C6/img/select_xiao_c6.png" alt="choose board" width="500"></li>
  <li>Download this repo, go in folder esp/esp32c6xiao and open .ino file</li>
</ol>

<h2>Setup and Start</h2>
You are downloading absolutely compleate Multi-End Point Occumancy Sensor. You do not need to edit it. But if you want customize - I made its realy easy.
<h3>Connection of sensors in my Example</h3>
Pin 18 - External Led;<br>
Buttons are 22 and 23 pins.
<table>
  <caption>
    Connection of Sensors
  </caption>
  <thead>
    <tr>
      <th>PIR</th>
      <th>HLK-LD2450n</th>
      <th>ESP</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>GND</th>
      <th>GND</th>
      <th>GND</th>
    </tr>
    <tr>
      <th>-</th>
      <th>5V</th>
      <th>VBUS</th>
    </tr>
    <tr>
      <th>3V</th>
      <th></th>
      <th>3V</th>
    </tr>
    <tr>
      <th>OUT</th>
      <th>-</th>
      <th>21</th>
    </tr>
    <tr>
      <th>-</th>
      <th>RX</th>
      <th>TX</th>
    </tr>
    <tr>
      <th>-</th>
      <th>TX</th>
      <th>RX</th>
    </tr>
  </tbody>
</table>

<h3>Customisation</h3>
<ol>
  <li>
    How to add build arguments:<br>
    Open file build_opt.h and add argumens.<br>
    <b>Dont ad Spaces or Enter after the end or betwen arguments!</b>
  </li>
  <li>
    How to edit time zone on your (only hardcodding):
    Open .ino file and go on 34 Line
  </li>
  <li>
    How to choose BLE commising or Wi-Fi (Wi-Fi only hardcodding):<br>
    Open variables.h file, go on line 4 and choose 1/0 1 - BLE, 0 - Wi-Fi. <br>
    Line 7 SSID of Wi-Fi, Line 8 - Passwod of Wi-Fi.
  </li>
  <li>
    Where are Matter Event file:<br>
    Open MEvent.h file and here you can add/remove/edit events.<br>
    <a href="https://github.com/espressif/arduino-esp32/blob/master/libraries/Matter/examples/MatterEvents/MatterEvents.ino">Matter All Events Example</a>
  </li>
  <li>
    How to make custom events on click Boot Button:<br>
    Open custom_connection.h and go on Line 18, then write your event.
  </li>
  <li>
    How to make custom events on Decommissioning:<br>
    Open custom_connection.h and go on Line 14, then write your event.
  </li>
  <li>
    Where are is better to declare variable?<br>
    If it is for global use - variables.h or for certelnal EP use sensor_name/sensor.h (hile of EP).
  </li>
  <li>
    How to add End Points (EP):
    <ul>
      <li>in root directory / create folder for example MatterOnOffLight (only in English!)</li>
    <li>
        Create functions:<br>
      
    static bool setLightOnOff(bool state) {} // For Logic (Not necessarily)
    static void OnOffLogicBeforeSetup(void*) {} // For setup EP (before Matter.beggin;)
    void OnOffinSetup(void*) {} // After Matter.beggin; in void setup
    void OnOffinLoop(void*) {} // In Loop
    
   If you will not use one or more of the functions you still have to create it but it can be empty.
   </li>
   <li>
     Declarate variables for Prefs and indicate Device Type
     
    const char *nsName = "MatterPrefs";
    const char *onOffKey = "OnOff";
   </li>
   <li>
     Open include.h file and after // ===== Matter EndPoint ===== add your variable
     
     /* On/Off Light */
    MatterOnOffLight OnOffPir;
   </li>
   <li>
     In OnOffLogicBeforeSetup add 
     
     OnOffPir.begin(); 

  and

    OnOffPir.onChange(setLightOnOff); // not necessarily
   </li>
   <li>
     To add remember of last state:
     
    bool lastPirState = matterPref.getBool(onOffPrefKeyPir, false);
    PirON = lastPirState; // Sync of flag
  </li>
  <li>
    Open DeviceImport.h and add functions LogicBeforeSetup, inSetup, inLoop:

    { &OnOffLogicBeforeSetup, &OnOffinSetup, &OnOffinLoop },
  </li>
  <li>
    Add logic to compilation. Open include.h and after // ===== Logic ===== add your file with logic of sensor.
    
    #include <MatterOnOffLight/MatterOnOffLight.h>
  </li>
  </ul>
  <li>Open folder ScanToAdd then open QR.png or README.md then open your home app > ADD > Matter or just scan QR. Setup code in README.md</li>
</ol>
