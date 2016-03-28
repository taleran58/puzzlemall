<font size='3'><b>PuzzleMall - A vulnerable web application for practicing session puzzling</b></font><br><br>
Developed by <a href='http://www.hacktics.com'>Hacktics ASC</a><br>
<a href='http://www.hacktics.com'><img src='http://diviner.googlecode.com/files/hacktics_logo.jpg' /></a><br>
PuzzleMall is a vulnerable web application designed for training purposes.<br>
<br>
It is prone to a variety of different session puzzle exposures,<br>
which can be detected and exploited using different session puzzling sequences. <br>
<br>
<b>About Session Puzzles</b><br>
Session puzzles are application-level vulnerabilities that were explained in a white paper released in May 17, 2011, by Hacktics ASC, Ernst&Young Security Excellence Center.<br>
These unique attack vectors enable attacker to execute <b>a new breed of logical attacks</b>, as well as enhance the capabilities of "traditional" attacks by constructing attack payloads in a server-side memory storage which is seemingly trusted (the session), and abusing these payloads to execute attacks in locations that were previously unreachable or considered safe.<br>
The white paper and presentation can be downloaded from the downloads section, in addition to the PuzzleMall application in "war" and source code distributions.<br>
<br>

<b>About Temporal Session Race Conditions (TSRC) and Layer Targeted ADoS</b><br>
Although the original session puzzling attack vector relied on the existence of persistent session values, an extended attack was presented in September 15, 2011, in a local OWASP chapter meeting.<br>
The extended attack (nicknamed "Temporal Session Race Conditions") enables detecting & exploiting session puzzles even if the session variables have a lifespan of milliseconds (session-level race conditions), by increasing the latency of certain lines of code through the use of layer targeted denial of service attacks.<br>
<br>

<u><b>Demo</b></u><br>
<b>The following short movies demonstrate a few simple session puzzling sequences:</b><br>
<a href='http://www.youtube.com/watch?v=-DackF8HsIE'>Authentication Bypass via Session Puzzling (Abusing common session variables)</a><br>
<a href='http://www.youtube.com/watch?v=ikIyInm0wAg'>User Impersonation via Session Puzzling (Abusing common session variables)</a><br>
<a href='http://www.youtube.com/watch?v=iTcOooHbgog'>Session Puzzling via Redirection Prevention (Abusing Premature Session Population)</a><br>
<a href='http://www.youtube.com/watch?v=HeP54b52IeQ'>Bypassing Restrictions in Multiphase Processes via Session Puzzling (Abusing Common Session Flags)</a><br>

<b>The following movies demonstrate a few simple TSRC attacks:</b><br>
<a href='http://www.youtube.com/watch?v=woWECWwrsSk'>Exploiting Temporal Session Race Conditions via Connection Pool Consumption</a><br>
<a href='http://www.youtube.com/watch?v=3k_eJ1bcCro'>Exploiting Temporal Session Race Conditions via RegEx DoS</a><br>
<br>

<font size='5'><b>Developers</b></font><br>
PuzzleMall is developed and maintained by <a href='http://twitter.com/sectooladdict/'>Shay Chen</a>.<br>
<br>
<b><u>Implementation</u></b><br>
PuzzleMall is implemented in Java/JSP, and uses apache derby as a data repository<br>
(and thus, requires no database installation).<br>

<b><u>Requirements</u></b><br>
JDK 1.6.x+<br>
Tomcat 6.x+ (should work on any JEE compliant application server / servlet container)<br>

<b><u>Potential Issue:</u></b> Due to the usage of the default derby-db location, might require the tomcat user to have admin/root permissions under linux/win7. Will be fixed ASAP.<br>
<br>
<b><u>Installation (Derby Version - Session Puzzling)</u></b><br>

(1) Download & install <a href='http://tomcat.apache.org/download-60.cgi'>apache tomcat 6.x</a><br>

(2) Copy the application war file into the tomcat webapps directory <br>
<blockquote>(Usually "C:\Program Files\Apache Software Foundation\Tomcat 6.0\webapps" - Windows 32/64 Installer)<br></blockquote>

(3) Restart the application server<br>

(4) On <b>WinXP</b>, as long as you are using a high privileged user - you can skip this phase,  on <b>Win7</b>, make sure you run the tomcat server with administrative privileges (right click on and execute),and on <b>Ubuntu Linux</b>, run the following commands:<br>
<blockquote><i>sudo mkdir /var/lib/tomcat6/db</i><br>
<i>sudo chown tomcat6:tomcat6 /var/lib/tomcat6/db/</i><br></blockquote>

(5) Initiate the install script at: <a href='http://localhost:8080/puzzlemall/install/initialize.jsp'>http://localhost:8080/puzzlemall/install/initialize.jsp</a><br>

(6) Access the application at: <a href='http://localhost:8080/puzzlemall/'>http://localhost:8080/puzzlemall/</a><br>
<br>

<b><u>Installation (MySQL Version - Temporal Session Race Conditions)</u></b><br>

(1) Download & install <a href='http://tomcat.apache.org/download-60.cgi'>apache tomcat 6.x</a><br>

(2) Download & install <a href='http://dev.mysql.com/downloads/mysql/'>MySQL Community Server 5.5.x</a> - and make sure remote root access is enabled (at least for the installation) <br>


(3) Copy the application war file into the tomcat webapps directory <br>
<blockquote>(Usually "C:\Program Files\Apache Software Foundation\Tomcat 6.0\webapps" - Windows 32/64 Installer)<br></blockquote>

(4) Restart the application server<br>

(5) On <b>WinXP</b>, as long as you are using a high privileged user - you can skip this phase,  on <b>Win7</b>, make sure you run the tomcat server with administrative privileges (right click on and execute),and on <b>Ubuntu Linux</b>, run the following commands:<br>
<blockquote><i>sudo mkdir /var/lib/tomcat6/db</i><br>
<i>sudo chown tomcat6:tomcat6 /var/lib/tomcat6/db/</i><br></blockquote>

(6) Initiate the install script at: <a href='http://localhost:8080/puzzlemall/install/initialize.jsp'>http://localhost:8080/puzzlemall/install/initialize.jsp</a><br>

(7) Provide the database host, port and root credentials to the installation script.<br>

(8) Access the application at: <a href='http://localhost:8080/puzzlemall/'>http://localhost:8080/puzzlemall/</a><br>