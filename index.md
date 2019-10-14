---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "swc"    # what kind of Carpentry (must be either "lc" or "dc" or "swc").  
                      # Be sure to update the Carpentry type in _config.yml as well.  
venue: "University of Arizona"        # brief name of host site without address (e.g., "Euphoric State University")
address: "Please check your email for the workshop location!"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latlng: "32.231901,-110.9495000"       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use https://www.latlong.net/)
humandate: "Oct 26-27, 2019"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "8:30 am - 5:00 pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2019-10-26      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2019-10-27        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Noah Nelson", "Sateesh Peri", "Kelsey	Gonzalez", "Xue Pan", "Travis Struck", "Uwe Hilgert"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Drake	Asberry", "Brian	Bell", "Jennifer	Kadowaki", "David	LeBauer", "Torbet	McNeil", "Erica	Newman", "Cristian Palacios", "Adriana	Picoral", "Fernando Rios", "Austin	Rutherford", "Saren	Seeley", "Marnee Dearman"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["hilgert@bio5.org"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---


<p><h4><center><strong>Apply for the workshop at <a href="http://bit.ly/356EkJl" target='blank'>http://bit.ly/356EkJl</a>.</strong></center></h4></p>

<h2 id="general">General Information</h2>

{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
{% endcomment %}
{% if page.carpentry == "swc" %}
{% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
{% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
{% include lc/intro.html %}
{% endif %}

{% comment %}
AUDIENCE

Explain who your audience is.  (In particular, tell readers if the
workshop is only open to people from a particular institution.
{% endcomment %}
{% if page.carpentry == "swc" %}
{% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
{% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
{% include lc/who.html %}
{% endif %}

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. They should have a few specific software packages installed (listed <a href="#setup">below</a>).
</p>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<p id="code-of-conduct">
<strong>Code of Conduct:</strong>  Everyone who participates in Carpentries activities is required to adhere to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>. This document also outlines how to report an incident if needed.
</p>


{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to anyone.
  The workshop organisers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  Links to workshop materials will be provided below. If we can provide additional resources to help making learning easier for you (e.g. large-font hand-outs, sign-language interpreters, lactation facilities) please get in touch (using contact details below) and we will attempt to provide them.
</p>
<!--<p>
  Materials will be provided in advance of the workshop and
  large-print handouts are available if needed by notifying the
  organizers in advance.  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>-->

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment %} 
SURVEYS - DO NOT EDIT SURVEY LINKS 
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop.</p>
{% if site.carpentry == "swc" %} 
<p><a href="{{ site.swc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.swc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif site.carpentry == "dc" %}
<p><a href="{{ site.dc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.dc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif site.carpentry == "lc" %}
<p><a href="{{ site.lc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.lc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% endif %}

<hr/>

{% comment %}
  SCHEDULE -- The original Schedule template is utterly messed up in that it (1) includes the link to the surveys which should be getting thier own header, and (2) does not allow to change the schedule template/tables. We are therefore using a table made from scratch and will not display the schedule included with the template.
{% endcomment %}


<h2 id="schedule">Schedule</h2>

<div class="row">
  <div class="col-md-6">
    <h3>Saturday October 26</h3>
    <table class="table table-striped">
       <tr> <td>08:30</td>  <td><a href="http://swcarpentry.github.io/shell-novice/" target="_blank">Automate tasks with the Unix shell</a> and <a href="http://swcarpentry.github.io/git-novice/" target="_blank">git/GitHub</a></td> </tr>
      <tr> <td>10:30</td> <td>Coffee</td> </tr>
      <tr> <td>12:00</td>  <td>Lunch break</td> </tr>
      <tr> <td>13:00</td>  <td>Unix shell/git/GitHub, cont.</td> </tr>
      <tr> <td>14:45</td>  <td>Coffee</td> </tr>
      <tr> <td>15:00</td>  <td><a href="http://swcarpentry.github.io/r-novice-gapminder/" target="_blank">Scientific Analyses with R</a> and <a href="http://swcarpentry.github.io/git-novice/" target="_blank">git/GitHub</a></td> </tr>
      <tr> <td>17:00</td>  <td>End of Day</td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Sunday October 27</h3>
    <table class="table table-striped">
      <tr> <td>08:30</td>  <td><a href="http://swcarpentry.github.io/r-novice-inflammation/" target="_blank">Scientific Analyses with R</a> and <a href="http://swcarpentry.github.io/git-novice/" target="_blank">git/GitHub</a>, cont.</td> </tr>
      <tr> <td>10:30</td>  <td>Coffee</td> </tr>
      <tr> <td>12:00</td>  <td>Lunch break</td> </tr>
      <tr> <td>13:00</td>  <td>R/R-Studio/git/GitHub, cont.</td> </tr>
      <tr> <td>14:45</td>  <td>Coffee</td> </tr>
      <tr> <td>17:00</td>  <td>End of Day</td> </tr>
    </table>
  </div>
</div>

<p>Schedule subject to change if necessary.</p>

{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

http://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="https://pad.carpentries.org/2019-10-26-Tucson">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

{% comment %}
SYLLABUS

Show what topics will be covered.

1. If your workshop is R rather than Python, remove the comment
around that section and put a comment around the Python section.
2. Some workshops will delete SQL.
3. Please make sure the list of topics is synchronized with what you
intend to teach.
4. You may need to move the div's with class="col-md-6" around inside
the div's with class="row" to balance the multi-column layout.

This is one of the places where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}
<h2 id="syllabus">Syllabus</h2>

<h2 id="syllabus">Syllabus & Learning Objectives</h2>

<div class="row">
  <div class="col-md-6">
	  <h3 id="syllabus-shell">Take control with the Unix Shell</h3>
    <ul>
	    <li>Work <em>in</em> vs. work <em>below</em> the GUI</li>
	    <li>Navigate the shell</li>
	    <li><code>Find</code>, create, copy, move and delete folders and files</li>
	    <li>Shell over GUI: Command history and tab completion</li>
	    <li>Connect commands into workflows: pipes and redirection</li>
	    <li>Automate repetitive tasks: loops</li>
	    <li>Save and run workflows in scripts</li>
	  </ul>
	  <u>Resources:</u>
	  <ul>
		  <li><a href="{{site.swc_pages}}/shell-novice">Shell Lessons</a></li>
		  <li><a href="{{site.swc_pages}}/shell-novice/reference/">Shell Quick Reference</a></li>
		  <li><a href="http://explainshell.com/" target="_blank"><em>Explain Shell</em> (Parses shell commands and shows docs about the command)</a></li>
		  <li><a href="http://www.shellcheck.net/" target="_blank"><em>ShellCheck</em> (Identifies bugs in shell scripts)</a></li>
		  <li><a href="http://man.he.net/" target="_blank"><em>Linux Man Pages Online</em> (Same content as command line man/help pages in the Unix shell)</a></li>
	  </ul>
  </div>
	
  <div class="col-md-6">
	  <h3 id="syllabus-r">Write analysis programs in R</h3>
    <ul>
	    <li>Work with vectors and data frames</li>
	    <li>Read and plot data</li><li>Create and use functions</li>
	    <li>Create loops and conditionals</li><li>Use R from the command line</li>
	  </ul>
	  <u>Resources:</u>
	  <ul>
		  <li><a href="{{site.swc_pages}}/r-novice-gapminder">R Lessons</a></li>
		  <li><a href="{{site.swc_pages}}/r-novice-gapminder/reference">R Quick Reference</a></li>
		  <li><a href="https://www.rdocumentation.org/" target="_blank">R documentation</a></li>
		  <li><a href="http://blog.moertel.com/posts/2006-01-20-wondrous-oddities-rs-function-call-semantics.html" target="_blank">R function call Semantics</a></li>
		  <li><a href="https://www.r-bloggers.com/" target="_blank">R News and Tutorials contributed by over 600 R Bloggers</a></li>
		  <li><a href="http://rmarkdown.rstudio.com/" target="_blank">R Markdown Site/Docs</a></li>
		  <li><a href="https://www.tutorialspoint.com/r/r_operators.htm" target="_blank">Tutorial: R Operators</a></li>
		  <li><a href="https://github.com/OHI-Science/ohicore/issues/104" target="_blank">Instructions to fix password error when pushing from RStudio</a></li>
	  </ul>
  </div>
  
	<!-- https://swcarpentry.github.io/git-novice/ -->
	
<div class="row">
  <div class="col-md-6">
	  <h3 id="syllabus-git">Collaborate with git/GitHub</h3>
    <ul>
	    <li>Access a repository and pull files</li>
	    <li>Create a repository</li>
	    <li>Record changes: <code>add</code>, <code>commit</code>, ...</li>
	    <li>View changes: <code>status</code>, <code>diff</code>, ...</li>
	    <li>Ignore files</li>
	    <li>Work on the web: <code>clone</code>, <code>pull</code>, <code>push</code>, ...</li>
	    <li>Resolve conflicts</li>
	  </ul>
	  <u>Resources:</u>
	  <ul>
		  <li><a href="{{site.swc_pages}}/git-novice">Git Lessons</a></li>
		  <li><a href="{{site.swc_pages}}/git-novice/reference">Git Quick Reference</a></li>
		  <li><a href="https://git-scm.com/book/en/v2/Git-in-Other-Environments-Git-in-Bash" target="_blank"><i>Mac/Linux:</i> Integrating Git into your shell prompt</a></li>
		  <li><a href="https://github.com/magicmonty/bash-git-prompt" target="_blank">An informative and fancy bash prompt for Git users</a></li>
		  <li><a href="https://education.github.com/pack" target="_blank">Unlimited <em>private</em> repositories for free on Github, <i>while you are a student</i></a></li>
		  <li><a href="https://git-annex.branchable.com/" target="_blank">Git for Archiving Data</a></li>
	  </ul>
  </div>
</div>
  
  <hr/>
  <hr/>

<h2 id="setup">Computer Preparation</h2>

<p>
  To participate in the
  {% if page.carpentry == "swc" %}
  Software Carpentry
  {% elsif page.carpentry == "dc" %}
  Data Carpentry
  {% elsif page.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  workshop,
  you will need access to the software described below. Unless you prepare your laptop as described below you will be unable to follow along.
  In addition, you will need an up-to-date web browser, we recommend Firefox, Chrome or Safari as Internet Explorer/Edge can be buggy.
</p>
<p>
<em>Should you encounter issues</em> while installing the software below, please look for a solution in our
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
If even this does not help, please get in touch with us using contact details above and we will attempt to provide a solution.
</p>

<hr/>

<div id="shell"> {% comment %} Start of 'shell' section. {% endcomment %}
  <h3>The Bash Shell (a.k.a. Command Line/Shell/Unix)</h3>

  <p>
    Bash is a commonly-used shell (= Unix command language) that gives you the power to quickly do simple tasks on your computer. Bash stands for 'Bourne Again Shell'; if you are interested in the history of the term and the underlying technological development, please search the Web for 'Bash Shell'.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="shell-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=339AEqk9c-8">Video Tutorial</a>
      <ol>
        <li>Download the Git for Windows <a href="https://git-for-windows.github.io/">installer</a>.</li>
        {% comment %}  "Do you want to run this file?" {% endcomment %}
      <li>Run the installer and follow the steps bellow:
          <ol>
            {% comment %}  "Information" {% endcomment %}
            <li>Click on "Next" four times (two times if you've previously installed Git). You don't need to change anything in the Information, location, components, and start menu screens.</li>
            {% comment %}  "Choosing Default Editor" {% endcomment %}
            <li>From the dropdown menu select "<strong>Use the nano editor by default</strong>" and click on "Next".</li>
            {% comment %} "Adjusting your PATH environment" {% endcomment %}
	   <li>Ensure that "<strong>Git from the command line and also from 3rd-party software</strong>" is selected and click on "Next". (If you don't do this gitbash will not work properly, requiring you to <strong>remove the GitBash installation, re-run the installer</strong> and to select the "Git from the command line and also from 3rd-party software" option.)</li>
	  {% comment %} Choosing the SSH executable {% endcomment %}
            <li>Ensure that "<strong>Use the native Windows Secure Channel library</strong>" is selected and click on "Next".</li>
            {% comment %} Configuring the line ending conversions {% endcomment %}
            <li>Ensure that "<strong>Checkout Windows-style, commit Unix-style line endings</strong>" is selected and click on "Next".</li>
            {% comment %} Configuring the terminal emulator to use with Git Bash {% endcomment %}
	    <li>Ensure that "<strong>Use Windows' default console window</strong>" is selected and click on "Next".</li>
            {% comment %} Configuring experimental performance tweaks {% endcomment %}
            <li>Ensure that "<strong>Enable file system caching</strong>" and "<strong>Enable Git Credential Manager</strong>"                              are selected and click on "Next".</li>
           <li>Click on "Install".</li>
            {% comment %} Installing {% endcomment %}
            {% comment %} Completing the Git Setup Wizard {% endcomment %}
            <li>Click on "Finish".</li>
          </ol>
        </li>
        <li>
          If your "HOME" environment variable is not set (or you don't know what this is):
          <ol>
            <li>Open command prompt (Open Start Menu then type <code>cmd</code> and press [Enter])</li>
            <li>
              Type the following line into the command prompt window exactly as shown:
              <p><code>setx HOME "%USERPROFILE%"</code></p>
            </li>
            <li>Press [Enter], you should see <code>SUCCESS: Specified value was saved.</code></li>
            <li>Quit command prompt by typing <code>exit</code> then pressing [Enter]</li>
          </ol>
        </li>
      </ol>
      <p>This will provide you with both Git and Bash in the Git Bash program.</p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-macosx">macOS</h4>
      <p>
        The default shell in all versions of macOS is Bash, so no
        need to install anything.  You access Bash from the Terminal
        (found in
        <code>/Applications/Utilities</code>).
        See the Git installation <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a>
        for an example on how to open the Terminal.
        You may want to keep
        Terminal in your dock for this workshop.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-linux">Linux</h4>
      <p>
        The default shell is usually Bash, but if your
        machine is set up differently you can run it by opening a
        terminal and typing <code>bash</code>.  There is no need to
        install anything.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'shell' section. {% endcomment %}

<hr/>

<div id="editor"> {% comment %} Start of 'editor' section. {% endcomment %}
  <h3>Text Editor</h3>
<p>
Writing code is much easier with respectively optimized text editors that include features such as automatic color-coding of key words and syntax-highlighting. We will use the basic editor '<strong>nano</strong>' in the workshop; it comes pre-installed with the git-bash download above for Windows, Mac and Linux.
</p>

<div class="row">
    <div class="col-md-4">
      <h4 id="editor-windows">Windows</h4>
<p>
	Click the Start button and type 'git bash' into the search window.<br> 
	Click on the "Git Bash" icon to open the shell.<br>
	Type 'nano test.txt' to open a text editor. <strong>If this does not open the nano text editor contact the workshop administrator at the email listed above.</strong><br>
	Type 'Test'.<br>
	To exit the nano editor press Ctrl and type 'x' (a.k.a. '^X'; additional commands are listed at the bottom of the text edito window.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-macosx">macOS</h4>
      <p>
        During the workshop we will be using the basic editor nano. nano should be pre-installed; see the Git installation <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a> for an example on how to open nano.        
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-linux">Linux</h4>
      <p>
        During the workshop we will be using the basic editor nano. nano should be pre-installed
      </p>
</div>
</div>
</div> {% comment %} End of 'editor' section. {% endcomment %}

<hr/>

<div id="git"> {% comment %} Start of 'Git' section. GitHub browser compatability
           is given at https://help.github.com/articles/supported-browsers/{% endcomment %}
  <h3>Git</h3>
  <p>
    Git is a version control system that lets you track who made changes
    to what when and has options for easily updating a shared or public
    version of your code
    on <a href="https://github.com/">github.com</a>. You will need a
    <a href="https://help.github.com/articles/supported-browsers/">supported</a>
    web browser (current versions of Chrome, Firefox or Safari,
    or Internet Explorer version 9 or above).
  </p>
  <p>
	  <strong>For the workshop you will need a GitHub account,</strong> if you don't have one already please get it at <a href="https://github.com/">github.com</a>. Basic GitHub accounts are free. However, please consider what personal information you'd like to reveal. For example, you may want to review these <a href="https://help.github.com/articles/keeping-your-email-address-private/">instructions for keeping your email address private</a> at GitHub.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="git-windows">Windows</h4>
      <p>
        Git should be installed on your computer as part of your Bash
        install (described above).
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="git-macosx">macOS</h4>
      <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">Video Tutorial</a>
      <p>
        <strong>For OS X 10.9 and higher</strong>, install Git for Mac
        by downloading and running the most recent "mavericks" installer from
        <a href="http://sourceforge.net/projects/git-osx-installer/files/">this list</a>.
        Because this installer is not signed by the developer, you may have to
        right click (control click) on the .pkg file, click Open, and click
        Open on the pop up window. 
        After installing Git, there will not be anything in your <code>/Applications</code> folder,
        as Git is a command line program.
        <strong>For older versions of OS X (10.5-10.8)</strong> use the
        most recent available installer labelled "snow-leopard"
        <a href="http://sourceforge.net/projects/git-osx-installer/files/">available here</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="git-linux">Linux</h4>
      <p>
        If Git is not already available on your machine you can try to
        install it via your distro's package manager. For Debian/Ubuntu run
        <code>sudo apt-get install git</code> and for Fedora run
        <code>sudo dnf install git</code>.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'Git' section. {% endcomment %}

<hr/>

<div id="r"> {% comment %} Start of 'R' section. {% endcomment %}
  <h3>R</h3>

  <p>
    <a href="https://www.r-project.org">R</a> is a programming language
    that is especially powerful for data exploration, visualization, and
    statistical analysis. To interact with R, we use
    <a href="https://www.rstudio.com/">RStudio</a>.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="r-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=q0PjTAylwoU">Video Tutorial</a>
      <p>
        Install R by downloading and running
        <a href="https://cran.r-project.org/bin/windows/base/release.htm">this .exe file</a>
        from <a href="https://cran.r-project.org/index.html">CRAN</a>.
        Also, please install the
        <a href="https://www.rstudio.com/products/rstudio/download/#download">RStudio IDE</a>.
        Note that if you have separate user and admin accounts, you should run the 
        installers as administrator (right-click on .exe file and select "Run as 
        administrator" instead of double-clicking). Otherwise problems may occur later, 
        for example when installing R packages.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-macosx">macOS</h4>
      <a href="https://www.youtube.com/watch?v=5-ly3kyxwEg">Video Tutorial</a>
      <p>
        Install R by downloading and running
        <a href="https://cran.r-project.org/bin/macosx/R-latest.pkg">this .pkg file</a>
        from <a href="https://cran.r-project.org/index.html">CRAN</a>.
        Also, please install the
        <a href="https://www.rstudio.com/products/rstudio/download/#download">RStudio IDE</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-linux">Linux</h4>
      <p>
        You can download the binary files for your distribution
        from <a href="https://cran.r-project.org/index.html">CRAN</a>. Or
        you can use your package manager (e.g. for Debian/Ubuntu
        run <code>sudo apt-get install r-base</code> and for Fedora run
        <code>sudo dnf install R</code>).  Also, please install the
        <a href="https://www.rstudio.com/products/rstudio/download/#download">RStudio IDE</a>.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'R' section. {% endcomment %}
