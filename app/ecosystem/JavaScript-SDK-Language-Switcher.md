---
id: page-plugin
title: Qordoba - JavaScript SDK Language Switcher
header_title: Qordoba - JavaScript SDK Language Switcher
header_icon: /assets/images/icons/plugins/GitHub-enterprise-integration.png
breadcrumbs:
  Plugins: /ecosystem
nav:
  - label: Getting Started
    items:
      - label: Configuration
  - label: Usage
    items:
      - label: Sending parameters
      - label: Known Issues
---
If you don't want to use URL mapping to automatically translate pages, you need to give users a way to manually change languages. This simple widget allows users to translate the page by simply selecting a language from the menu. 

In the Javascript snippet below, we have provided some common configuration options. If these options don't meet your needs, you should change the HTML/CSS/JS source code as needed.

You can find all of the source code on our <a href='https://github.com/Qordobacode/language-switcher-js-sdk/tree/master'> Github page </a>.

### HTML

Create a new anchor tag with the same structure for each language you offer, and ensure the language codes are correct.

```
<!-- Insert into <head> and change src/href paths as needed -->
<link rel="stylesheet" type="text/css" href="./main.css">
<script src='./main.js' type="text/javascript"></script>
<script type="text/javascript" src='http://qcdn.qordoba.com/qordoba-latest.min.js'></script>


<!-- Insert directly into <body> -->
<div class="qordoba-dropdown">
  <button onclick="toggleDropdown()" class='qordoba-dropbtn'> Select language </button>
    <div id='qordoba-myDropdown' class='qordoba-dropdown-content'>
      <!--Create another <a> tag for each of your languages -->
      <a onclick='handleSelect(this)' selected='selected' data-langcode='en-us'>
      English
      </a>
      <a onclick='handleSelect(this)' data-langcode='de-de'>
      German
      </a>
    </div>
</div>
```

### CSS

Basic styling and positioning for the dropdown menu. 

```
/* Dropdown Button */
.qordoba-dropbtn {
    background-color: #4CAF50;
    color: white;
    padding: 16px;
    font-size: 10px;
    border: none;
    cursor: pointer;
    font-family: sans-serif;
}

/* The container <div> - needed to position the dropdown content */
.qordoba-dropdown {
    position: relative;
    display: inline-block;
    font-family: sans-serif;
}

/* Dropdown Content (Hidden by Default) */
.qordoba-dropdown-content {
    display: none;
    position: absolute;
    background-color: #f9f9f9;
    min-width: 160px;
    box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
    z-index: 1;
    font-size: 10px;
}

/* Links inside the dropdown */
.qordoba-dropdown-content a {
    color: black;
    padding: 12px 16px;
    display: block;
}

/* Change color of dropdown links on hover */
.qordoba-dropdown-content a:hover {background-color: #f1f1f1}

/* Show the dropdown menu */
.qordoba-show {display:block;}

/* Position the dropdown menu */
.qordoba-topLeft{ 
  position: absolute;
  top: 0px;
  left: 0px;
} 

.qordoba-topRight{ 
  position: absolute;
  top: 0px;
  right: 0px;
}
```

### Javascript

Javascript to render the dropdown and attach necessary event listeners. Configuration options are available to you here.

```
/*
  Config options:
    flag: true OR false
    location: topLeft, topRight
    refreshPageOnTranslation: true OR false
    dropdownColor: Any color (default: green)
    dropdownTextColor: ''
*/

var config = {
  flag: true,
  location: 'topLeft',
  refreshPageOnTranslation: true,
  dropdownColor: '',
  dropdownTextColor: ''
}

var checkForFlags = () => {
  if (config.flag) {
    var languageOptions = document.querySelector('#qordoba-myDropdown').children;

    for (var i = 0; i < languageOptions.length; i++) {
      var countryCode = languageOptions[i].dataset.langcode.split('-')[1];
      var flagToBeAppended = document.createElement('img');

      flagToBeAppended.src = `https://raw.githubusercontent.com/tkrotoff/famfamfam_flags/master/${countryCode}.png`;
      flagToBeAppended.align = 'right';

      languageOptions[i].appendChild(flagToBeAppended);
    }
  }
}

var setDropdownPosition = () => {
  var dropdown = document.getElementsByClassName('qordoba-dropdown')[0];

  dropdown.classList.add(`qordoba-${config.location}`);

  if (config.location.slice(0,3) === 'top') {
    document.body.style.paddingTop = `${dropdown.clientHeight}px`
  }
  else {
    document.body.style.paddingBottom = `${dropdown.clientHeight}px`
  }
}

var setDropdownColor = () => {
  var dropdownButton = document.getElementsByClassName('qordoba-dropbtn')[0];
  if (config.dropdownColor.length) {
    dropdownButton.style.backgroundColor = config.dropdownColor;
  }
  if (config.dropdownTextColor.length) {
    dropdownButton.style.color = config.dropdownTextColor;
  }
}

var handleSelect = (context) => {
  if (!Qordoba) {
    console.error('Qordoba SDK not foundd')
  }
  else {
    Qordoba.translate(context.dataset.langcode, config.refreshPageOnTranslation)
  }
}

/* When the user clicks on the button, 
toggle between hiding and showing the dropdown content */
var toggleDropdown = () => {
    document.getElementById("qordoba-myDropdown").classList.toggle("qordoba-show");
}

// Close the dropdown menu if the user clicks outside of it
window.onclick = (event) => {
  if (!event.target.matches('.qordoba-dropbtn')) {

    var dropdowns = document.getElementsByClassName("qordoba-dropdown-content");
    var i;
    for (i = 0; i < dropdowns.length; i++) {
      var openDropdown = dropdowns[i];
      if (openDropdown.classList.contains('qordoba-show')) {
        openDropdown.classList.remove('qordoba-show');
      }
    }
  }
}

var init = () => {
  checkForFlags();
  setDropdownPosition();
  setDropdownColor();
}

document.addEventListener('DOMContentLoaded', () => {
  init()
});
```
