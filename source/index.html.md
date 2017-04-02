---
title: API Reference

language_tabs:
  - html
  - javascript
  - css

toc_footers:
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

search: true
---

# Introduction

Welcome to the Blue Dashboard! You can use our dashboard to manage your business easily, where you can get information and statistics through charts, tables, modals and more.

Blue Dashboard is built using modern Bootstrap according to high standards in UX/UI design.

This Documentation will help you to use the dashboard effectively.

## Getting Started

You can use blue dashboard to add multiple features and pages in your website, all you have to do is to <a href="https://github.com/new-release/Blue-dashboard">download our dashboard or fork it from github</a>.

### Features

The features provided by the Blue dashboard:

  * Dashboard

  * Forms
    - Forms Elements
    - Forms Wizard

  * Charts

  * Email

  * UI Elements
    - Icons
    - Colors
    - Buttons
    - Notifications
    - Modals
    - Tabs
    - Cards
    - Loading & progress
    - Panels
    - Lists
    - Menus
    - Hover

  * Calendar

  * App Views 
    - Account management
    - Landing page
    - Chat View
    - Social

  * Tables
    - Basic table
    - Data table

  * Maps
    - Vector maps
    - Google maps

  * Extra
    - Invoice
    - 404 page
    - 500 page
    - Login & registration 
    - Lock screen
    - Tour

### Configs 

Blue dashboard uses a variety of plugins and libraries so in order for you to make use of the feature in your website you will need to include some files first.

Those file are mandatory for the use of the dashboard features.

```html
<!-- Jquery Framework -->

<script type="text/javascript" src="assets/vendors/jquery/jquery-3.1.1.js"></script>

<!-- Bootstrap Framework -->

<link type="text/css" href="assets/vendors/bootstrap/css/bootstrap.min.css" rel="stylesheet">

<script type="text/javascript" src="assets/vendors/bootstrap/js/bootstrap.min.js"></script>

<!-- Google fonts -->

<link type="text/css" href="assets/vendors/google-fonts/google-fonts.css" rel="stylesheet">

<!-- Font Awesome library -->

<link type="text/css" href="assets/vendors/font-awesome/css/font-awesome.min.css" rel="stylesheet" />

<!-- Blue dashboard style -->

<link type="text/css" href="assets/css/style.css" rel="stylesheet" />

<!-- Blue dashboard main JS file -->

<script type="text/javascript" src="assets/js/main.js"></script>

<!-- Blue dashboard notifications JS file -->

<script type="text/javascript" src="assets/js/notifications_boxs.js"></script>


```

## <a href="https://gruntjs.com/getting-started">Grunt</a>

In one word: automation. The less work you have to do when performing repetitive tasks like minification, compilation, unit testing, linting, etc, the easier your job becomes. After you've configured it through a Gruntfile.

### Getting started 

In Blue dashboard we decided to use a node application by using <a href="https://www.npmjs.com/">npm</a>.
When creating a node application you will need a file called package.json to manage local npm packages.'

> package.json file

```javascript
{
  "name": "my_package",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "https://github.com/ashleygwilliams/my_package.git"
  },
  "author": "",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/ashleygwilliams/my_package/issues"
  },
  "homepage": "https://github.com/ashleygwilliams/my_package",
  "devDependencies": {
    "grunt": "^1.0.1",
    "grunt-contrib-less": "^1.4.0",
    "grunt-contrib-sass": "^1.0.0 ",
    "grunt-contrib-watch": "^1.0.0"

  }
}

```
> Gruntfile

```javascript

module.exports = function(grunt) {
  grunt.loadNpmTasks('grunt-contrib-less');  //Load grunt less task
  grunt.loadNpmTasks('grunt-contrib-sass');  //Load grunt sass task
  grunt.loadNpmTasks('grunt-contrib-watch'); //Load grunt watch task
  // Project configuration.
  grunt.initConfig({
    pkg: grunt.file.readJSON('package.json'),

    sass: {
      dist: {
        files: {
          'assets/css/dist_file': 'assets/scss/source_file'  //Compile SCSS file
        }
      }
    },
    less: {
      development: {
        options: {
          paths: ['assets/less']
        },
        files: {
          'assets/css/dist_file': 'assets/less/source_file' //Compile LESS file
        }
      }
    },
    watch:{
      less:{
        files:['assets/less/your_less_file.less'], //monitor LESS files for changes
        tasks:['less']
      },
    }
  });
};

```

### installation

* In Blue dashboard we decided to use a node application by using npm to compile the SASS and LESS files into CSS files.
The following commands should be be used in the terminal.
  
  - Install the grunt CLI globally by running this command `npm install -g grunt-cli` using the terminal.
  - To initialize the nodejs project, you can run `npm init` in the same project directory, then go through the preparations steps.
  - Create Gruntfile manually in your project directory and keep it empty.
  - Install the npm desired packages:
      - `npm install grunt --save-dev`
      - `npm install grunt-contrib-less --save-dev`
      - `npm install grunt-contrib-sass --save-dev`
      - `npm install grunt-contrib-watch --save-dev`
  - You will notice these packages being added under devDependencies in package.json.
  - In the gruntfile add the following code as shown in the example.
  - Now you can use the grunt commands to compile your LESS and SASS files:
      - Use `Grunt less` to compile less files.
      - Use `Grunt sass` to compile sass files.
      - Use `Grunt watch` to keep track of the less or sass files.

<aside class="success">
Grunt watch is used to keep track of your less or sass files to compile them immediately when saving changes to the file. 
</aside>

* package.json file (example on the right) contains information such as :

  - name: the current directory name
  - version: always 1.0.0
  - description: info from the readme, else an empty string ""
  - main: always index.js
  - scripts: by default creates a empty test script
  - keywords: empty
  - author: empty
  - license: ISC
  - bugs: info from the current directory, if present
  - homepage: info from the current directory, if present

<aside class="success">
Please note that the node application is not the only way that could be used, for example you can use <a href="http://koala-app.com/">Koala</a> to compile SASS.
</aside>


## LESS

Less is a CSS pre-processor, meaning that it extends the CSS language, adding features that allow variables, mixins, functions and many other techniques that allow you to make CSS that is more maintainable, themeable and extendable.

* In the LESS directory you will find a mix of files and folders :
  - Global - Contains the variables file that includes the general variables used in the dashboard.
  - Utilities - Contains the features provided by the dashboard such as inputs, cards etc.
  - Views - Contains the dashboard's pages design.
  - Base.less - Contains the basic and most general styles of the dashboard.
  - Imports.less - Is probably the most important file in the directory for the fact that it contains the imports of all the LESS files.
  - main.less - Contains a less general styles than the base.less


## SASS

Sass is an extension of CSS that adds power and elegance to the basic language. It allows you to use variables, nested rules, mixins, inline imports, and more, all with a fully CSS-compatible syntax.

* In the SCSS directory you will find a mix of files and folders :
  - Global - Contains the variables file that includes the general variables used in the dashboard.
  - Utilities - Contains the features provided by the dashboard such as inputs, cards etc.
  - Views - Contains the dashboard's pages design.
  - Base.scss - Contains the basic and most general styles of the dashboard.
  - Imports.scss - Is probably the most important file in the directory for the fact that it contains the imports of all the SCSS files.
  - main.scss - Contains a less general styles than the base.less

# Forms

## Form Elements
Our Forms feature provides a variety of customized forms elements such as input fields, check boxes, date pickers, etc.

### Input Fields

Blue Dashboard provide a collection of input fields that you can easily use in your website.

All you need to do is to include Blue Dashboard customized CSS file in addition to <a href="http://materializecss.com/">materializecss</a> framework JS file.

> To use our customized input fields:

```html

<!-- materialize JS file -->

<script type="text/javascript" src="assets/vendors/materialize/materialize.min.js"></script>

<!-- Basic input field -->

<div class="input-field">
    <input id="full_name" name="full_name" type="text" class="validate">
    <label for="full_name">Full Name*</label>
</div>

<!-- Input field with icon -->

<div class="input-field">
    <i class="material-icons prefix">
        <i class="fa fa-user" aria-hidden="true"></i>
    </i>
    <input id="user_prefix" name="email" type="text" class="validate user_prefix">
    <label for="user_prefix" class="user_prefix">Username</label>
</div>
```
### Ranges

In order to use the Ranges slider you will have to include two CSS files the first one defines the basic look for the slider and the second one for the theme you choose in addition to the JS file for the library.



<aside class="notice">
Don't forget to initialize the range in the javascript 
</aside>
> To use our ranges:

```html
<!-- ionrange slider library -->

<link type="text/css" rel="stylesheet" href="assets/vendors/ion-slider/css/ion.rangeSlider.css">

<link type="text/css" href="assets/vendors/ion-slider/css/ion.rangeSlider.skinNice.css">

<script type="text/javascript" src="assets/vendors/ion-slider/js/ion.rangeSlider.min.js"></script>

<!-- Slider container -->

<input type="text" id="no-params" name="example_name" value="" />
```

```javascript
$('#no-params').ionRangeSlider();
```
### Toggles

If you wanted to use the slide toggles all you need to do is include Blue Dashboard styles file.


You can also change the color of the toggle by using one of the colors classes such as: <br>
<code>.ch-toggle-green</code> <br>
<code>.ch-toggle-red</code> 
> To use slide toggle:

```html
<!-- toggle switch element -->

<div class="toggleswitch">
    <input id="toggle-checked" class="ch-toggle ch-toggle-green" type="checkbox">
    <label for="toggle-checked"></label>
</div>
```
### Dropdown Select

The dropdown selects are a very common input tool so in order to use them you should include the link for the Select2 CSS file and JS file.

The dropdown select includes variety of features such as: <br>
<code>.select2-init-single</code> <br>
<code>.select2-init-multiple</code> <br>
<code>.select2-init-images</code>
<aside class="notice">
Don't forget to initialize the select dropdown in the javascript 
</aside>
> To use select dropdown:

```html
<!-- Select2 library -->

<link type="text/css" rel="stylesheet" href="assets/vendors/select2/css/select2.min.css">

<script type="text/javascript" src="assets/vendors/select2/js/select2.min.js"></script>

<!-- Dropdown element -->

<select class="select-display select2-init-single selectpicker">
    <option value="Oklahoma">Oklahoma</option>
    <option value="Newyork">New york</option>
    <option value="California">California</option>
    <option value="Texas">Texas</option>
    <option value="Florida">Florida</option>
</select>
```
```javascript
$('.select2-init-single').select2();
$('.select2-init-multiple').select2();
$('.select2-init-images').select2({
  templateResult: formatState
});
```

### Checkboxes

In Blue Dashboard you can find many checkboxes styles such as colored checkboxes, circled checkboxes and yes/no checkboxes.


In order to use the colored checkboxes all you need to do is to include Blue Dashboard styles file.<br>

As for the yes/no checkboxes you need to include a JS file for the <a href="https://vsn4ik.github.io/bootstrap-checkbox/">Bootstrap checkbox</a> library as shown in the example. <br>

<aside class="notice">
Don't forget to initialize the yes/no checkbox in the javascript 
</aside>
> To use checkboxes:

```html
<!-- Bootstrap checkbox library -->

<script type="text/javascript" src="assets/vendors/checbox-picker/dist/js/bootstrap-checkbox.min.js"></script>

<!--  Colored checkboxes: -->

<div class="checkbox">
    <input id="checkbox1" type="checkbox" checked>
    <label class="fontsize" for="checkbox1"> A simple checkbox </label>
</div>

<!-- Circle checkboxes: -->

<div class="checkbox checkbox-circle">
    <input id="checkbox-circle-default" type="checkbox">
    <label for="checkbox-circle-default">Default</label>
</div>
```
```javascript
$('#toggleCheckbox-yes-green').checkboxpicker();
```

### Datepickers
Blue Dashboard provides many datepickers styles including range datepickers, simple datepickers and advanced datepickers.

In order to use range datepickers you need to include the <a href="http://www.daterangepicker.com/">date range picker library </a> as shown in the example.



In addition to datepickers you can use clockpicker by including the <a href="https://weareoutman.github.io/clockpicker/">clock picker library</a> as shown in the example.

You can also use the advanced datepicker by including the <a href="http://t1m0n.name/air-datepicker/docs/"> air datepicker library</a> as shown in the example.

<aside class="notice">
Don't forget to initialize the range datepickers in the javascript 
</aside>
> To use datepickers:

```html
<!-- Date eange picker library -->

<link type="text/css" rel="stylesheet" href="assets/vendors/datepickers/daterangepicker.css" />

<script type="text/javascript" src="daterangepicker.js"></script>

<!-- clock picker library -->

<script type="text/javascript" src="assets/vendors/datepickers/daterangepicker.js"></script>

<script type="text/javascript" type="text/javascript" src="assets/vendors/clockpicker/bootstrap-clockpicker.min.js"></script>

<!-- air datepicker library -->

<link type="text/css" rel="stylesheet" href="assets/vendors/air-datepicker/css/datepicker.min.css">

<script type="text/javascript" src="assets/vendors/air-datepicker/js/datepicker.min.js"></script>

<script type="text/javascript" src="assets/vendors/air-datepicker/js/datepicker.en.js"></script>
<!-- Range Datepicker -->

<input type="text" name="daterange" class="form-control simple" value="01/01/2015 1:30 PM - 01/01/2015 2:00 PM" />

<!-- Predefined Ranges -->

<div id="reportrange" class="simple data-range">
    <i class="glyphicon glyphicon-calendar fa fa-calendar"></i>&nbsp;
    <span></span> <b class="caret"></b>
</div>

<!-- Simple datepicker -->

<input type="text" name="birthdate" class="form-control simple" value="10/24/1984" />

<!-- clock picker -->

<div class="input-group clockpicker simple" data-placement="right" data-align="top" data-autoclose="true">
  <input type="text" class="form-control" value="13:14">
  <span class="input-group-addon">
    <span class="glyphicon glyphicon-time"></span>
  </span>
</div>

<!-- air datepicker -->

<div class="datepicker-here simple" data-language='en'></div>
```

```javascript
// Range Datepicker:

$('input[name="daterange"]').daterangepicker({
  timePicker: true,
  timePickerIncrement: 30,
  locale: {
    format: 'MM/DD/YYYY h:mm A'
  }
});

// Predefined ranges:

$('#reportrange').daterangepicker({
  startDate: start,
  endDate: end,
  ranges: {
    'Today': [moment(), moment()],
    'Yesterday': [moment().subtract(1, 'days'), moment().subtract(1, 'days')],
    'Last 7 Days': [moment().subtract(6, 'days'), moment()],
    'Last 30 Days': [moment().subtract(29, 'days'), moment()],
    'This Month': [moment().startOf('month'), moment().endOf('month')],
    'Last Month': [moment().subtract(1, 'month').startOf('month'), moment().subtract(1, 'month').endOf('month')]
  }
}, cb);

// Simple datepicker:

$('input[name="birthdate"]').daterangepicker({
  singleDatePicker: true,
  showDropdowns: false
});

// Clockpicker

$('.clockpicker').clockpicker();

// Advanced datepicker
$('.datepicker-here').datepicker();

```
### Tag Inputs

You can use Tag Inputs to insert tags into input fields and in order to do that all you need to do is include the files of the <a href="https://bootstrap-tagsinput.github.io/bootstrap-tagsinput/examples/">Bootstrap Tags Input</a> as shown in the example.

<aside class="notice">
The objects tags amd the categorized tags needs to be initialized in javascript and the the values added to them there.
</aside>
> To use the tags inputs:

```html
<!-- Tags input library -->

<link type="text/css" rel="stylesheet" href="assets/vendors/tag-input/bootstrap-tagsinput.css">

<script type="text/javascript" src="assets/vendors/tag-input/bootstrap-tagsinput.js"></script>

<script type="text/javascript" src="assets/vendors/tag-input/typeahead.bundle.min.js"></script>

<!-- Markup -->

<input type="text" value="Amsterdam,Washington" data-role="tagsinput" />

<!-- True multi value -->

<select multiple data-role="tagsinput">
    <option value="Amsterdam">Amsterdam</option>
    <option value="Washington">Washington</option>
</select>

<!-- Objects as tags -->
                                    
<input class="objects-as-tags" type="text" />


<!-- Categorizing tags -->

<input class="colored-tags" type="text" />

```

```javascript
// Objects as tags

var typeaheadTags = $('.objects-as-tags');
typeaheadTags.tagsinput({
  itemValue: 'value',
  itemText: 'text',
  typeaheadjs: {
    name: 'cities',
    displayKey: 'text',
    source: cities.ttAdapter()
  }
});

typeaheadTags.tagsinput('add', {
  'value': 1,
  'text': 'Amsterdam',
  'continent': 'Europe'
});

//Categorizing tags

var typeaheadColored = $('.colored-tags');
typeaheadColored.tagsinput({
  tagClass: function(item) {
    switch (item.continent) {
      case 'Europe':
        return 'label label-primary';
      case 'America':
        return 'label label-danger label-important';
      case 'Australia':
        return 'label label-success';
      case 'Africa':
        return 'label label-default';
      case 'Asia':
        return 'label label-warning';
    }
  },
  itemValue: 'value',
  itemText: 'text',
  typeaheadjs: {
    name: 'cities',
    displayKey: 'text',
    source: cities.ttAdapter()
  }
});
typeaheadColored.tagsinput('add', {
  'value': 1,
  'text': 'Amsterdam',
  'continent': 'Europe'
});
typeaheadColored.tagsinput('add', {
  'value': 4,
  'text': 'Washington',
  'continent': 'America'
});
```

### Drag N' Drop

If you want to add an upload field we have just the solution for you with the Drag N' Drop input.

You can use this feature by including the <a href="http://www.dropzonejs.com/">dropzone JS library</a> as shown in the example.


> To use the drop zone:

```html
<!-- dropzone library -->

<link type="text/css" rel="stylesheet" href="assets/vendors/drop-zone/dropzone.css">

<script type="text/javascript" src="assets/vendors/drop-zone/dropzone.js"></script>

<!-- Dropzone container -->

<div class="dropzone-min">
    <form action="/file-upload" class="dropzone" id="my-awesome-dropzone"></form>
</div>
```

### Text Editor

In order to use the customized text editor you will have to include the <a href="http://summernote.org/">summernote library</a> as shown in the example.

> To use the text editor:

```html
<!-- Summernote library -->

<link href="assets/vendors/summernote/summernote.css" rel="stylesheet">
<script type="text/javascript" src="assets/vendors/summernote/summernote.js"></script>

<!-- Customized textarea -->

<link type="text/css" rel="stylesheet" href="assets/css/text-editor.css">

<!-- Textarea container -->

<div id="summernote">hello </div>

```

```javascript
$('#summernote').summernote({
  height: 200
});

```

## Form Wizard


The form wizard form is an easier way to gather information and easier for the user to fill the form that way.

Blue dashboard wizard is based on the <a href="http://vinceg.github.io/twitter-bootstrap-wizard/">twitter bootstrap wizard </a> library so you will have to include the JS file of that library as shown in the example.

* Blue dashbaord form wizard uses 2 libraries by default :
  - Select2 library
  - Sweet alert library 

So in order to use the wizard you will need Blue dashboard style file in addition to these 2 libraries files.

<aside class="notice">
Don't forget to include the JS file of the form wizard itself as shown in the example.
</aside>
```html
<!-- twitter bootstrap wizard library -->

<script type="text/javascript" src="assets/vendors/twitter-bootstrap-wizard/jquery.bootstrap.wizard.min.js"></script>
<!-- Select2 library -->

<link type="text/css" rel="stylesheet" href="assets/vendors/select2/css/select2.min.css">

<script type="text/javascript" src="assets/vendors/sweet-alert/sweetalert.min.js"></script>

<!-- Sweet alert library -->

<link type="text/css" rel="stylesheet" href="assets/vendors/sweet-alert/sweetalert.css">

<script type="text/javascript" src="assets/vendors/sweet-alert/sweetalert.min.js"></script>

<!-- Form wizard JS file -->

<script type="text/javascript" src="assets/js/form-wizard.js"></script>

```

# Email

* The email page provides two responsive sub-pages that you can use :
  - Inbox page.
  - Compose page.

* In order to use those pages all you need to do is to include the files as shown in the example and copy the source from it's page in the blue dashboard main directory and paste it into your project.

```html
<!-- INBOX PAGE-->
<!-- Text editor and summernote CSS -->

<link rel="stylesheet" href="assets/css/text-editor.css">

<link href="assets/vendors/summernote/summernote.css" rel="stylesheet">

<script src="assets/vendors/summernote/summernote.js"></script>

<!-- moment.js -->

<script src="assets/vendors/momentjs/moment.js"></script>

<!-- Inbox page JS -->

<script src="assets/js/inbox.js"></script>


<!-- COMPOSE PAGE -->
<!-- Tags input library -->

<link type="text/css" rel="stylesheet" href="assets/vendors/tag-input/bootstrap-tagsinput.css">

<script type="text/javascript" src="assets/vendors/tag-input/bootstrap-tagsinput.js"></script>

<!-- Text editor and summernote CSS  -->

<link type="text/css" rel="stylesheet" href="assets/css/text-editor.css">

<link href="assets/vendors/summernote/summernote.css" rel="stylesheet">

<!-- Compose page JS -->

<script type="text/javascript" src="assets/js/compose.js"></script>


```
# UI Elements

UI Elements are a very important utility to use in your website and they are very useful and give a very nice addition to any website.

In Blue Dashboard we gathered a set of elements that you will find useful and very easy to use.

## Notifications

You can use Blue Dashboard notifications in your website very easily all you have to do is include the blue dashboard styles file and :

- Choose which of the listed libraries you wish to use. <br>

1- Bootstrap alert. <br>
2- Sweet alert. <br>
3- Toastr alert.

- Include their files. <br>

1- Bootstrap alert. <br>

 * Use the `.alert` class to initialize the bootstrap alert in addition to the color classes such as :
  - `.alert-success` & `.success-lighter`.

2- Sweet alert <br>


 * Initialize the sweet alert in the JS using `swal("Message")` function which can include many options such as :
  - `type: 'warning'`, to determine the type of the alert.


3- Toastr alert. <br>


 * Initialize toastr alert in the JS using `toastr['info']('Bottom Right!');` . You will have to pass the type of the alert in the function as shown before and give it a text to display, you can also control the position of the alert using it's options just by adding :
  - `toastr.options = {'positionClass': 'toast-bottom-center'}`;

```html

<!-- Bootstrap CSS file -->

<link type="text/css" href="assets/vendors/bootstrap/css/bootstrap.min.css" rel="stylesheet">

<!-- Sweet alert library -->

<link type="text/css" rel="stylesheet" href="assets/vendors/sweet-alert/sweetalert.css">

<script type="text/javascript" src="assets/vendors/sweet-alert/sweetalert.min.js"></script>

<!-- Toastr alert library -->

<link type="text/css" href="assets/vendors/toastr/toastr.css" rel="stylesheet" />

<script type="text/javascript" src="assets/vendors/toastr/toastr.js"></script>

<!-- Bootstrap success alert -->

<div class="alert alert-success success-lighter">
    <strong>Success!</strong> Indicates a successful or positive action.
</div>
```

```javascript

// Sweet alert

swal("Here's a message!")

// Toastr alert

toastr.options = {
    'positionClass': 'toast-bottom-right',
    'onclick': null,
    'showDuration': '300',
    'hideDuration': '1000',
    'timeOut': '5000',
    'showMethod': 'fadeIn',
    'hideMethod': 'fadeOut'
};

toastr['info']('Bottom Right!');

```
## Colors

### Primary

<img src="images/primary.png">

### Info

<img src="images/info.png">

### Success

<img src="images/danger.png">

### Warning

<img src="images/warning.png">

### Danger

<img src="images/danger.png">

### Default

<img src="images/default.png">


## Icons

Blue Dashboard include the popular font icons libraries, <a target href="http://fontawesome.io/">fontawesome</a> and <a href="http://getbootstrap.com/components/">glyphicons</a>.

<img src="images/icons.png">

### Fontawesome

Just include the icon class like the HTML sample to use it in the dashboard.


```html
<!-- Font awesome -->

<link type="text/css" href="assets/vendors/font-awesome/css/font-awesome.min.css" rel="stylesheet" />

<!-- Bootstrap glyphicons -->

<link type="text/css" href="assets/vendors/bootstrap/css/bootstrap.min.css" rel="stylesheet">

<!-- Font awesome usage -->

<i class="fa fa-user-circle" aria-hidden="true"></i>

<!-- glyphicon usage -->

<span class="glyphicon glyphicon-asterisk"></span>

```

### Glyphicons
Just include the icon class like the HTML sample to use it in the dashboard.

```html

```

## Modals

The modals we use are extracted from <a href="https://v4-alpha.getbootstrap.com/components/modal/"> bootstrap framework modals </a> with a little bit of customizing on them.

* All you have to do is :
 - Include the blue dashboard style file and initialize the modal in the HTML file.
 - Use the Blue dashboard customization classes such as `.right` to use the right side modal.

* Some modals don't require customization classes such as the flat modal as shown in the example.

* You can open and close the modal in two ways:
 - Using the `data-toggle="modal"` & `data-target="#flat-modal"` attributes.
 - Using `modal( )` method.
 
```html
<!-- Right side modal -->

<!-- Open modal -->
<button id="modal-open" data-toggle="modal" data-toggle="modal" data-target="#right-side-modal">Open</button>

<!-- Modal -->
<div class="modal right fade" id="right-side-modal" tabindex="-1" role="dialog" aria-labelledby="right-side-modal-label">
    <div class="modal-dialog" role="document">
        <div class="modal-content">
            <div class="modal-header">
                <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
                <h4 class="modal-title" id="right-side-modal-label">Right Sidebar</h4>
            </div>
            <div class="modal-body custome-margin">
                <p class="right-modal-content"></p>
                <br>
                <div class="row">
                    <div class="col-sm-12">
                        <button type="button" class="btn btn-info center-block right-button">Action</button>
                    </div>
                </div>
                <div class="row">
                    <div class="col-sm-12">
                        <button type="button" class="btn btn-primary center-block right-button">Cancel</button>
                    </div>
                </div>
            </div>
        </div>
        <!-- modal-content -->
    </div>
    <!-- modal-dialog -->
</div>

<!-- Flat modal -->

<!-- Open modal --> 
<button id="flat-modal" data-toggle="modal" data-target="#flat-modal">Open</button>

<!-- Modal --> 
<div class="modal fade" id="flat-modal" tabindex="-1" role="dialog" aria-labelledby="flat-modal-label">
    <div class="modal-dialog" role="document">
        <div class="modal-body">
            <div class="jumbotron">
                <input type="text" placeholder="Type anywhere to search" class="form-control flat_email">
                <i class="fa fa-search glyphicon glyphicon-search" aria-hidden="true"></i>
            </div>
        </div>
    </div>
</div>

```

## Buttons

In Blue dashboard we used the same <a href="http://getbootstrap.com/css/#buttons">buttons in bootstrap</a> in addition to our own touch.

* If you wanted to use the Blue dashboard buttons all you need to do is :
   - Include the Blue dashboard style file.
   - Use the customized classes as shown in the example.

* Please note that if you wanted to use the buttons with hover you need to include the 
<a href="http://ianlunn.github.io/Hover/">Hover.css</a> library.

```html
<!-- Dashboard Buttons -->

<button type="button" class="btn btn-default">Default</button>
<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-success">Success</button>
<button type="button" class="btn btn-info">Info</button>
<button type="button" class="btn btn-warning">Warning</button>
<button type="button" class="btn btn-danger">Danger</button>
<button type="button" class="btn btn-default btn-block">Block Button</button>

<!-- Icon Buttons -->

<button type="button" class="btn btn-info icon-btn">
    <span class="glyphicon glyphicon-search"></span> Search
</button>

<!-- Icon Buttons -->

<button type="button" class="btn outline-primary">Primary</button>

<button class="btn btn-primary dropdown-toggle" type="button" data-toggle="dropdown">Dropdown Button
    <span class="caret"></span>
</button>
<ul class="dropdown-menu">
    <li><a>First Option</a></li>
    <li><a>Second Option</a></li>
    <li><a>Third Option</a></li>
</ul>

<!-- Grouped Buttons -->

<div class="btn-group">
    <button type="button" class="btn btn-primary">First Button</button>
    <button type="button" class="btn btn-primary">Second Button</button>
    <button type="button" class="btn btn-primary">Third Button</button>
</div>

<!-- Buttons With Hover -->

<button type="button" class="btn btn-success hvr-float">Success</button>

```

## Loading

Loaders could be used in many places but two main functionalities are when the user is waiting for a determinate  or indeterminate process.

* Progress bars and circles are used in determinate operations.

* Loaders are used in indeterminate operations.

* Progress circles. 
  - These progress shapes were extracted from the <a href="https://kimmobrunfeldt.github.io/progressbar.js/">PROGRESS BAR.JS</a> 
  - In order to use them you need to include ProgressBar.js Javascript file. <br>
  - You can manipulate and play with the progress circle options as you like using the options provided by the library.

* Progress bars.
  - Same as the Progress circles above you should include the ProgressBar.js Javascript file.

* Placeholder loader.
  - This famous loader is used as stand alone plugin meaning that it doesn't need any libraries, all you need to do is to include the blue dashboard Style file and use it just like the example does.

* Indeterminate loaders.
  - To use any of the indeterminate loaders all you need to do is to include the dashboard style file as before and do as the example shows.

<aside class="notice">
Please note that in blue dashboard the loaders are displayed and hidden using Jquery.
</aside>

```html

<!-- Progress bar.js library -->

<script type="text/javascript" src="assets/vendors/progressbar/progressbar.min.js"></script>

<!-- Progress bar-circle container -->

<div id="container"> </div>


<!-- Placeholder loader -->

<div class="timeline-item">
    <div class="animated-background facebook">
        <div class="background-masker header-top"></div>
        <div class="background-masker header-left"></div>
        <div class="background-masker header-right"></div>
        <div class="background-masker header-bottom"></div>
        <div class="background-masker subheader-left"></div>
        <div class="background-masker subheader-right"></div>
        <div class="background-masker subheader-bottom"></div>
        <div class="background-masker content-top"></div>
        <div class="background-masker content-first-end"></div>
        <div class="background-masker content-second-line"></div>
        <div class="background-masker content-second-end"></div>
        <div class="background-masker content-third-line"></div>
        <div class="background-masker content-third-end"></div>
    </div>
</div>

<!-- Indeterminate circle loader -->

<div class="loader1">
    <svg class="circular" viewBox="25 25 50 50">
        <circle class="path" cx="50" cy="50" r="20" fill="none" stroke-width="2" stroke-miterlimit="10" />
    </svg>
</div>

<!-- Indeterminate bar loader -->

<div class="loader"></div>

<!-- Indeterminate cube loader -->
<div id="loader" class="vertical--center">
    <div class="vertical-center__element">
        <span class="preloader preloader--top"></span>
        <span class="preloader preloader--bottom"></span>
    </div>
</div>

```

```javascript

// Progress circle initialization 

var bar = new ProgressBar.Circle(container, {
  strokeWidth: 6,
  easing: 'easeInOut',
  duration: 1400,
  color: '#FFEA82',
  trailColor: '#eee',
  trailWidth: 1,
  svgStyle: null
});

bar.animate(1.0);

// Progress bar initialization 

var bar = new ProgressBar.Line(container, {
  strokeWidth: 4,
  easing: 'easeInOut',
  duration: 1400,
  color: '#FFEA82',
  trailColor: '#eee',
  trailWidth: 1,
  svgStyle: {width: '100%', height: '100%'}
});

bar.animate(1.0);

```

## Cards

<a href="http://materializecss.com/cards.html">Cards</a> are a feature extracted from  <a href="http://materializecss.com/">Materialize framework </a>to display information in a new way.

You can use blue dashboard customized cards by including the blue dashboard style file in addition to the MaterializeCSS JS file and use the cards as shown in th example.



```html
<!-- Materialize JS -->

<script type="text/javascript" src="assets/vendors/materialize/materialize.min.js"></script>

<!-- Basic cards -->

<div class="card info-mid">
    <div class="card-content white-text">
        <span class="card-title">Card Title</span>
        <p>
        I am a very simple card. I am good at containing small bits of information. I am convenient because I require little markup to use effectively. I am similar to what is called a panel in other frameworks.
        </p>
    </div>
    <div class="card-action">
        <a href="#" class="default-dahsboard-link">This is a link</a>
        <a href="#" class="default-dahsboard-link">This is a link</a>
    </div>
</div>

<!-- Horizontal Card -->

<div class="card horizontal">
    <div class="card-image">
        <img alt="card title" src="assets/images/card_03.jpg">
    </div>
    <div class="card-stacked">
        <div class="card-content">
            <p>I am a very simple card. I am good at containing small bits of information.</p>
        </div>
        <div class="card-action">
            <button type="button" class="btn btn-link">This is a link<button>
        </div>
    </div>
</div>
<!-- Card reveal -->

<div class="card">
    <div class="card-image">
        <img alt="card title" class="activator" src="assets/images/card_02.jpg">
    </div>
    <div class="card-content">
        <span class="card-title activator grey-text text-darken-4">Card Title<i class="material-icons right">more_vert</i></span>
        <p>I am a very simple card.</p>
    </div>
    <div class="card-action">
        <button type="button" class="btn btn-link">This is a link</button>
    </div>
    <div class="card-reveal">
        <span class="card-title grey-text text-darken-4">Card Title<i class="material-icons right">close</i></span>
        <p>Here is some more information about this product that is only revealed once clicked on.</p>
    </div>
</div>

```


## Lists

Lists are an easy tool to use. Based on bootstrap lists blue dashboard lists provide a variety of options to use when listing your information.

All you need to do to start using blue dashboard's lists is to include the blue dashboard styles file.


<aside class="notice">
Please note that if you intend to use the toggle list you need to include the <a href="http://bootstrapswitch.com/">Bootstrap switch</a> library.
</aside>
```html
<!-- Basic list -->

<div class="list-group glyph-color">
    <a class="list-group-item">
        <div class="glyphicon glyphicon-text-size"></div> First item</a>
    <a class="list-group-item">
        <div class="glyphicon glyphicon-menu-hamburger"></div> Second item</a>
    <a class="list-group-item">
        <div class="glyphicon glyphicon-stats"></div> Third item</a>
    <a class="list-group-item">
        <div class="glyphicon glyphicon-send"></div> Forth item</a>
    <a class="list-group-item">
        <div class="glyphicon glyphicon-flash"></div> Fifth item</a>
</div>

<!-- Blog list -->

<div class="list-group">
    <a class="list-group-item">
        <div class="row">
            <div class="col-sm-3">
                <img src="assets/images/card_01.jpg" class="blog-img side-line">
            </div>
            <div class="col-sm-9">
                <span>Title goes here Title goes here Title goes here Title goes here. </span>
                <br>
                <p class="list-date">Oct 22, 2016</p>
            </div>
        </div>
    </a>
    <a class="list-group-item">
        <div class="row">
            <div class="col-sm-3">
                <img src="assets/images/card_02.jpg" class="blog-img side-line">
            </div>
            <div class="col-sm-9">
                <span>Title goes here Title goes here Title goes here Title goes here. </span>
                <br>
                <p class="list-date">Aug 20, 2017</p>
            </div>
        </div>
    </a>
</div>

<!-- List With Header -->

<ul class="list-group glyph-color">
    <li class="list-group-item">
        <div class="row">
            <div class="col-sm-10 no-padding-right">
                <h5 class="title-border">First</h5>
            </div>
            <div class="col-sm-2 no-padding-left">
                <div class="glyphicon glyphicon-flash icon-list-border"></div>
            </div>
        </div>
        <p class="box-size">Lorem ipsum dolor sit amet, cMaecenas ut fringilla libero. Nullam a rhoncus.</p>
    </li>
    <li class="list-group-item">
        <div class="row">
            <div class="col-sm-10 no-padding-right">
                <h5 class="title-border">Second</h5>
            </div>
            <div class="col-sm-2 no-padding-left">
                <div class="glyphicon glyphicon-text-size icon-list-border"></div>
            </div>
        </div>
        <p class="box-size">Lorem ipsum dolor sit amet, cMaecenas ut fringilla libero. Nullam a rhoncus.</p>
    </li>
    <li class="list-group-item">
        <div class="row">
            <div class="col-sm-10 no-padding-right">
                <h5 class="title-border">Third</h5>
            </div>
            <div class="col-sm-2 no-padding-left">
                <div class="glyphicon  glyphicon-stats icon-list-border"></div>
            </div>
        </div>
        <p class="box-size">Lorem ipsum dolor sit amet, consectetur adipiscing.</p>
    </li>
</ul>
```


## Hover

Using this library will provide a nice animation for the element that is used on.

In order to use the hovers you will need to include the <a href="http://ianlunn.github.io/Hover/">hover.css </a>library.

All you have to do is to put the class of the animation you want such as `.hvr-grow-rotate` to the desired element.

```html
<!-- Hover.css library -->

<link type="text/css" href="assets/css/hover-min.css" rel="stylesheet" />

<!-- Examples -->

<button class="hvr-pop">Pop</button>
<button class="hvr-bounce-in">Bounce In</button>
<button class="hvr-bounce-out">Bounce Out</button>
<button class="hvr-rotate">Rotate</button>
<button class="hvr-grow-rotate">Grow Rotate</buttona>
```

## Panels

In Blue dashboard panels you can use many types of panels such as collapsing panels and full screen panels or even draggable panels.

All you need to do is to include the blue dashboard style file and the panels JS file.


<aside class="notice">
Please note that if you want to use the drag and drop panel you need to include <a href="https://bevacqua.github.io/dragula/">Dragula</a> library in addition to the Drag and drop costume file as shown in the example.
</aside>


```html

<!-- Panels JS file -->

<script type="text/javascript" src="assets/js/panels.js"></script>


<!-- Dragula library -->

<link type="text/css" href="assets/css/dragula.css" rel="stylesheet" />

<script type="text/javascript" src="assets/js/dragula.js"></script>

<!-- Drag and drop costume file -->

<link type="text/css" href="assets/css/drag_drop.css" rel="stylesheet" />

<!-- Collapsible Panel -->

<div class="panel-group">
    <div class="panel panel-default no-borders">
        <div class="panel-heading dashboard-panel">
            Panel Heading
            <a data-toggle="collapse" data-target="#demo">
                <span class="glyphicon glyphicon-chevron-up float-right"></span>
            </a>
        </div>
        <div id="demo" class="panel-collapse collapse in">
            <div class="panel-body">
                <p>
                    Lorem Ipsum is simply dumtype setting industry. Lorem Ipstandard dummy text ever since the scrambled.
                </p>
            </div>
            <div class="panel-footer">Panel Footer</div>
        </div>
    </div>
</div>

<!-- Panels With Fullscreen -->

<div class="panel panel-default no-borders">
    <div class="panel-heading">
        Panel Heading
        <ul class="list-inline panel-actions">
            <li>
                <p id="panel-fullscreen" role="button" title="Toggle fullscreen"><i class="glyphicon glyphicon-resize-full"></i></li>
        </ul>
    </div>
    <div class="panel-body">
        <p>Lorem Ipsum is simply dummy text of the printing and typesetting 
        industry. Lorem Ipsum has been the industry's standard dummy text ever 
        since the scrambled Lorem Ipsum has been the industry's.
        </p>
    </div>
</div>

<!-- Panels With Contextual Classes -->

<div class="panel panel-primary">
    <div class="panel-heading primary-mid">Panel with panel-primary class</div>
    <div class="panel-body">Panel Content</div>
</div>
```


## Menu

You can use menus to categorize the information you want to display.

To use blue dashboard costume menus all you need to do is include the blue dashboard style file and after that proceed as it shows in the example.

```html
<!-- Side Menu -->

<div class="menu-container height-32">
    <nav class="navbar sidebar" role="navigation">
        <div class="navbar-header">
            <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#bs-sidebar-navbar-collapse-1">
                <span class="sr-only">Toggle navigation</span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
            </button>
            <a class="navbar-brand" href="#">Blue Dashboard</a>
        </div>
        <div class="collapse navbar-collapse" id="bs-sidebar-navbar-collapse-1">
            <ul class="nav navbar-nav">
                <li class="active">
                    <a>Home
                        <span class="pull-right hidden-xs showopacity glyphicon glyphicon-home"></span>
                    </a>
                </li>
                <li>
                    <a>Profile
                        <span  class="pull-right hidden-xs showopacity glyphicon glyphicon-user"></span>
                    </a>
                </li>
                <li>
                    <a>Messages
                        <span class="pull-right hidden-xs showopacity glyphicon glyphicon-envelope"></span>
                    </a>
                </li>
                <li class="dropdown">
                    <a class="dropdown-toggle" data-toggle="dropdown">Settings
                        <span class="caret"></span>
                        <span class="pull-right hidden-xs showopacity glyphicon glyphicon-cog"></span>
                    </a>
                    <ul class="dropdown-menu forAnimate" role="menu">
                        <li><a>Action</a></li>
                        <li><a>Another action</a></li>
                        <li><a>Something else here</a></li>
                    </ul>
                </li>
                <li>
                    <a>Home
                        <span class="pull-right hidden-xs showopacity glyphicon glyphicon-home"></span>
                    </a>
                </li>
                <li>
                    <a>Profile
                        <span class="pull-right hidden-xs showopacity glyphicon glyphicon-user"></span>
                    </a>
                </li>
                <li>
                    <a>Messages
                        <span class="pull-right hidden-xs showopacity glyphicon glyphicon-envelope"></span>
                    </a>
                </li>
            </ul>
        </div>
    </nav>
</div>


<!-- Simple Menu -->
<div class="menu-container">
    <nav class="navbar navbar-inverse">
        <div class="container-fluid">
            <ul class="nav navbar-nav">
                <li class="active"><a>Home</a></li>
                <li class="dropdown">
                    <a class="dropdown-toggle" data-toggle="dropdown" href="#">Services
                        <span class="caret"></span>
                    </a> 
                    <ul class="dropdown-menu">
                        <li><a>Services 1-1</a></li>
                        <li><a>Services 1-2</a></li>
                        <li><a>Services 1-3</a></li>
                    </ul>
                </li>
            </ul>
            <ul class="nav navbar-nav navbar-right">
                <li><a><span class="glyphicon glyphicon-user"></span> Sign Up</a></li>
                <li><a><span class="glyphicon glyphicon-log-in"></span> Login</a></li>
            </ul>
        </div>
    </nav>
</div>
```


## Tabs

Tabs gives a very nice display of data in your website.

In order to use this utility you will have to include blue dashboard style file in addition to the tabs JS file. 

```html

<!-- Customized tabs initialization -->

<script type="text/javascript" src="assets/js/taps.js"></script>

<!-- Bordered tab -->

<div class="tabs-container">
    <div class="tabs-header">
        <ul class="nav nav-tabs bordered-tab nav-style info-mid">
            <li class="active">
                <a data-toggle="tab" href="#home">Home&nbsp;
                    <span class="glyphicon glyphicon-home"></span>
                </a>
            </li>
            <li>
                <a data-toggle="tab" href="#menu1">About Us&nbsp;
                    <span class="glyphicon glyphicon-info-sign"></span>
                </a>
            </li>
            <li>
                <a data-toggle="tab" href="#menu2">Our Services&nbsp;
                    <span class="glyphicon glyphicon-star-empty"></span>
                </a>
            </li>
            <li>
                <a data-toggle="tab" href="#menu3">Contact Us&nbsp;
                    <span class="glyphicon glyphicon-send"></span>
                </a>
            </li>
        </ul>
    </div>
    <div class="tab-content">
        <div id="home" class="tab-pane fade in active">
            <h3 class="tabs-head-title">
                <span class="glyphicon glyphicon-home"></span>&nbsp;Default
            </h3>
            <hr>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do 
            eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
        </div>
        <div id="menu1" class="tab-pane fade">
            <h3 class="tabs-head-title">
                <span class="glyphicon glyphicon-info-sign"></span>&nbsp;About Us
            </h3>
            <hr>
            <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris 
            nisi ut aliquip ex ea commodo consequat.</p>
        </div>
        <div id="menu2" class="tab-pane fade">
            <h3 class="tabs-head-title">
                <span class="glyphicon glyphicon glyphicon-star-empty"></span>&nbsp;Our Services
            </h3>
            <hr>
            <p>Sed ut perspiciatis unde omnis iste natus error sit voluptatem 
            accusantium doloremque laudantium, totam rem aperiam.</p>
        </div>
        <div id="menu3" class="tab-pane fade">
            <h3 class="tabs-head-title">
                <span class="glyphicon glyphicon-send"></span>&nbsp;Contact Us
            </h3>
            <hr>
            <p>Eaque ipsa quae ab illo inventore veritatis et quasi architecto 
            beatae vitae dicta sunt explicabo.</p>
        </div>
    </div>
</div>
```

# Calendar

Blue Dashboard include a JavaScript event calendar using <a target="_blank" href="https://fullcalendar.io/">fullcalendar</a> library.
We customized the UI design for this view and its modals to be user friendly and easy to use. 

<img src="images/Pasted image at 2017_03_23 12_49 PM.png">

* In order to use the blue dashboard customized calendar you will have to include blue dashboard's style file in addition to the calendar files as shown in the example.

```html

<!-- fullcalendar library -->

<link href="assets/vendors/calendar/calendar_theme.css" rel="stylesheet" />
<link href='assets/vendors/calendar/fullcalendar.css' rel='stylesheet' />
<link href="assets/vendors/calendar/fullcalendar.print.css" rel='stylesheet' media='print' />
<script src="assets/vendors/calendar/lib/moment.min.js"></script>
<script src="assets/vendors/calendar/fullcalendar.min.js"></script>


<!-- fullcalendar customization and initialization file -->

<script src="assets/js/calendar.js"></script>


<!-- Calendar container -->

<div id='calendar'></div>

```

# Charts

Charts is a very effective way to display statistics.

* In blue Dashboard we used a couple of libraries to display charts: 
  - <a href="http://www.highcharts.com/">HIGH CHARTS. </a>
  - <a href="http://www.chartjs.org/">CHARTS JS. </a>

All you need to do to use them is to include the library JS file and then initialize the chart on a `div` in the html page.

```html
<!-- Highcharts library -->

<script type="text/javascript" src="highcharts.js"></script>

<!-- ChartJS library -->

<script type="text/javascript" src="chart.bundle.min.js"></script>


<!-- High charts -->

<div id="container4"></div>


<!-- Chart JS -->
<canvas id="line"></canvas>

```

```javascript

// High charts initialization

Highcharts.chart('container4', {
  chart: {
    margin: [20, 0, 80, 25],
  },
  xAxis: {
    min: -0.5,
    max: 5.5
  },
  yAxis: {
    min: 0
  },
  title: {
    text: ''
  },
  exporting: {
    buttons: [{
      symbol: '',
    }]
  },
  series: [{
    type: 'line',
    name: 'Regression Line',
    data: [
      [0, 1.11],
      [5, 4.51]
    ],
    marker: {
      enabled: false
    },
    states: {
      hover: {
        lineWidth: 0
      }
    },
    enableMouseTracking: false
  }, {
    type: 'scatter',
    name: 'Observations',
    data: [1, 1.5, 2.8, 3.5, 3.9, 4.2],
    marker: {
      radius: 4
    }
  }]
});

// Chart JS initialization

var ctx4 = document.getElementById('line');
var myLineChart = new Chart(ctx4, {
  type: 'line',
  data: {
    labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
    datasets: [{
      label: 'My First dataset',
      fill: true,
      lineTension: 0.1,
      backgroundColor: 'rgba(75,192,192,0.4)',
      borderColor: 'rgba(75,192,192,1)',
      borderCapStyle: 'butt',
      borderDash: [],
      borderDashOffset: 0.0,
      borderJoinStyle: 'miter',
      pointBorderColor: 'rgba(75,192,192,1)',
      pointBackgroundColor: '#fff',
      pointBorderWidth: 1,
      pointHoverRadius: 5,
      pointHoverBackgroundColor: 'rgba(75,192,192,1)',
      pointHoverBorderColor: 'rgba(220,220,220,1)',
      pointHoverBorderWidth: 2,
      pointRadius: 1,
      pointHitRadius: 10,
      data: [65, 59, 80, 81, 56, 55, 40],
      spanGaps: false,
    }]
  },
  options: {
    scales: {
      yAxes: [{
        ticks: {
          beginAtZero: true
        }
      }]
    }
  }
});
```


# Tables

## Basic Tables

Blue Dashboard use <a target="_blank" href="http://getbootstrap.com/css/#tables">Bootstrap</a> tables with custom design.
You can use any custom class with <code>table</code> tag to get the style.

* In order to use the basic tables all you need to do is to include the blue dashboard style file.

### Users Table Style

You juat need to add <code>.users-table</code> class to the table tag to get this style.

<img src="images/users_table.png"/>

```html

<!-- Users table -->

<table class="table table-hover users-table">
  <thead class="table-head">
    <tr>
      <th class="basic-th col-sm-3">User info.</th>
      <th class="basic-th col-sm-3">Job Description</th>
      <th class="basic-th col-sm-1">Country</th>
      <th class="basic-th col-sm-2">Email</th>
      <th class="basic-th col-sm-2">Last Update</th>
      <th class="basic-th col-sm-1">Activation</th>
    </tr>
  </thead>
  <tbody class="users-table-body">
      <tr class="active-user-acount">
        <td>
          <img src="assets/images/user_01_74.jpg" />
          <p><b>Sami Ali</b>
          <br> Project Manager</p>
        </td>
        <td>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</td>
        <td class="static-width">Jordan</td>
        <td class="email-field">email@domin.com</td>
        <td>April 13,2014 10:13</td>
        <td class="active-user-row"><i class="fa fa-thumbs-o-up info-font" aria-hidden="true"></i>&nbsp;Yes</td>
      </tr>
      <tr class="active-user-acount">
        <td>
          <img src="assets/images/user_02_74.jpg" />
          <p><b>Rania Jaber</b>
          <br> UI Designer</p>
        </td>
        <td >Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. </td>
        <td class="static-width">Lebanon</td>
        <td class="email-field">email@domin.com</td>
        <td>April 13,2014 10:13</td>
        <td class="active-user-row"><i class="fa fa-thumbs-o-up info-font" aria-hidden="true"></i>&nbsp;Yes</td>
      </tr>
      <tr class="active-user-acount">
        <td>
          <img src="assets/images/user_04_74.jpg" />
          <p><b>Albert Bailee</b>
          <br>Web Developer</p>
        </td>
        <td>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. </td>
        <td class="static-width">United States</td>
        <td class="email-field">email@domin.com</td>
        <td>April 13,2014 10:13</td>
        <td class="active-user-row"><i class="fa fa-thumbs-o-up info-font" aria-hidden="true"></i>&nbsp;Yes</td>
      </tr>
      <tr class="not-active-user-acount">
        <td>
          <img src="assets/images/user_03_74.jpg" />
          <p><b>Ria Yong</b>
          <br>Account Manager</p>
        </td>
        <td>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. </td>
        <td class="static-width">United States  </td>
        <td class="email-field">email@domin.com</td>
        <td>April 13,2014 10:13</td>
        <td class="not-active-user-row"><i class="fa fa-thumbs-o-down danger-font" aria-hidden="true"></i> &nbsp;No
        </td>
      </tr>
      <tr class="not-active-user-acount">
        <td>
          <img src="assets/images/user_06_74.jpg" />
          <p><b>Ali Mosa</b>
          <br>UX Researcher</p>
        </td>
        <td>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. </td>
        <td class="static-width">Jordan</td>
        <td class="email-field">email@domin.com</td>
        <td>April 13,2014 10:13</td>
        <td class="not-active-user-row"><i class="fa fa-thumbs-o-down danger-font" aria-hidden="true"></i> &nbsp;No</td>
      </tr>
  </tbody>
</table>
```

### Dashed Table Design

Just apply Dashed class(<code>.dashed-row-style</code>) to make the table Dashed style.

<img src="images/dashed_table.png" />

```html

<!-- Dashed Table -->

<table class="table dashed-row-style dashed-table">
  <thead class="table-head no-left-right-padding">
    <tr>
      <th class="basic-th col-sm-4">Operation Name</th>
      <th class="basic-th col-sm-3">From</th>
      <th class="basic-th col-sm-3">To</th>
      <th class="basic-th col-sm-2">Status</th>
    </tr>
  </thead>
  <tbody class="users-table-format">
    <tr class="active-user-acount no-left-right-padding">
      <td>
        <b>Requirements Gathering</b>
      </td>
      <td class="static-width">Jan, 18 Wednesday</td>
      <td class="email-field">February, 20 Thursday</td>
      <td class="email-field done-task"><i class="fa fa-check" aria-hidden="true"></i> &nbsp;Done
      </td>
    </tr>
    <tr class="active-user-acount">
      <td>
        <b>UX/UI Design</b>
      </td>
      <td class="static-width">Jan, 18 Wednesday</td>
      <td class="email-field">February, 20 Thursday</td>
      <td class="email-field done-task"><i class="fa fa-check" aria-hidden="true"></i> &nbsp;Done
      </td>
    </tr>
    <tr class="active-user-acount">
      <td>
        <b>Fron-end & Back-end Development</b>
      </td>
      <td class="static-width">Jan, 18 Wednesday</td>
      <td class="email-field">February, 20 Thursday</td>
      <td class="email-field inprogress-task"><i class="fa fa-spinner" aria-hidden="true"></i>&nbsp;Inprogress
      </td>
    </tr>
    <tr class="active-user-acount">
      <td>
        <b>Testing</b>
      </td>
      <td class="static-width">Jan, 18 Wednesday</td>
      <td class="email-field">February, 20 Thursday</td>
      <td class="email-field hold-task"><i class="fa fa-ban" aria-hidden="true"></i>&nbsp;Hold
      </td>
    </tr>
    <tr class="active-user-acount">
      <td>
        <b>Maintenance</b>
      </td>
      <td class="static-width">Jan, 18 Wednesday</td>
      <td class="email-field">February, 20 Thursday</td>
      <td class="hold-task"><i class="fa fa-ban" aria-hidden="true"></i>&nbsp;Hold
      </td>
    </tr>
  </tbody>
</table>
```
### Colored Table

You can change the table head color by adding any color class (eg:<code>.info-mid</code>).

## Data Tables

Blue Dashboard uses <a target="_blank" href="https://datatables.net/">DataTables</a> plug-in with custom design.
This plug-in include many features (search, sort, pagination, child rows, copy, export and more).

In order to use our customized Datatable you will need to include blue dashboard's style file in addition to the library files as shown in the example.

<aside class="notice">
You can read DataTables <a href="https://datatables.net/examples/index">documentation</a> to learn about plug-in options and features.
</aside>

```html

<!-- Datatable library -->

<script type="text/javascript" src="assets/vendors/datatables/media/js/jquery.dataTables.min.js"></script>

<script type="text/javascript" src="assets/vendors/datatables/extensions/Buttons/js/dataTables.buttons.min.js"></script>

<script type="text/javascript" src="assets/vendors/datatables/extensions/Buttons/js/buttons.html5.min.js"></script>

<script type="text/javascript" src="assets/js/data_table.js"></script>

<!-- Datatable -->

<table id="column_searching" class="table table-responsive">
    <thead class="table-head data-table-head">
        <tr>
            <th class="basic-th">Name</th>
            <th class="basic-th">Position</th>
            <th class="basic-th">Office</th>
            <th class="basic-th">Age</th>
            <th class="basic-th">Start date</th>
            <th class="basic-th">Salary</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Tiger Nixon</td>
            <td>System Architect</td>
            <td>Edinburgh</td>
            <td>61</td>
            <td>2011/04/25</td>
            <td>$320,800</td>
        </tr>
        <tr>
            <td>Garrett Winters</td>
            <td>Accountant</td>
            <td>Tokyo</td>
            <td>63</td>
            <td>2011/07/25</td>
            <td>$170,750</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <th>Name</th>
            <th>Position</th>
            <th>Office</th>
            <th>Age</th>
            <th>Start date</th>
            <th>Salary</th>
        </tr>
    </tfoot>
</table>

```


# App Views

## Account Management

You can manage your personal banking accounts using the account management view.
<br>
<br>
<img src="images/account_managment.png">

* Account management View includes :
  - Account management library.
  - Date Picker. (Check the forms section for further information)
  - Charts. (Check the charts section for further information)
  - DataTables. (Check the tables section for further information)

### 

```html

<!-- Account management library -->

<script type="text/javascript" src="assets/js/account-manager.js"></script>

<!-- Date Picker -->

<link type="text/css" rel="stylesheet" type="text/css" href="assets/vendors/air-datepicker/css/datepicker.min.css">

<script type="text/javascript" src="assets/vendors/air-datepicker/js/datepicker.min.js"></script>
<script type="text/javascript" src="assets/vendors/air-datepicker/js/datepicker.en.js"></script>

<!-- Charts -->

<script type="text/javascript" src="assets/vendors/highcharts/highcharts.js"></script>
<script type="text/javascript" src="assets/vendors/highcharts/modules/data.js"></script>
<script type="text/javascript" src="assets/vendors/highcharts/modules/exporting.js"></script>

<!-- DataTables -->

<script type="text/javascript" src="assets/vendors/datatables/media/js/jquery.dataTables.min.js"></script>
<script type="text/javascript" src="assets/vendors/datatables/extensions/Buttons/js/dataTables.buttons.min.js"></script>
<script type="text/javascript" src="assets/vendors/datatables/extensions/Buttons/js/buttons.html5.min.js"></script>

```

## Landing Page

* Landing page includes 6 sections :
  - Showcase Video.
  - Features (Using <a target="_blank" href="https://owlcarousel2.github.io/OwlCarousel2/"> OWL Carousel </a>Library).
  - Technologies.
  - Our Team.
  - Pricing.
  - Map (Using Google Map API).


<br><br>
<img src="images/landing_page.png">

```html

<!-- Owl carousel library -->

<link rel="stylesheet" href="assets/vendors/owlcarousel/owl.carousel.css">

<link rel="stylesheet" href="assets/vendors/owlcarousel/owl.theme.default.min.css">

<script src="assets/vendors/owlcarousel/highlight.js"></script>

<script src="assets/vendors/owlcarousel/app.js"></script>

<script src="assets/vendors/owlcarousel/owl.carousel.js"></script>

<!-- Landing page JS file -->

<script src="assets/js/landing_map.js"></script>

<!-- Google API -->

<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyB0bxmUytZ20M6YA2DA7auQPOB97kzjlHw&callback=initMap" async defer></script>

```

## Chat View

Blue Dashboard include a full chat application view with many features like create a new channel or start a new direct conversation with any user, you can also send many types of messages (text, image, youtube video..)


<img src="images/chat_view.png">

### Create Channel Modal

<img src="images/creat_channel.png">

### Direct Messages Modal

<img src="images/direct_message.png">

* All you need to do to use this page is to include the blue dashboard style file in addition to the chat JS file as shown in the example.

```html
<!-- Chat JS file -->

 <script src="assets/js/chat.js"></script>

```

## Social

You can use Blue Dashboard social view for any social timeline. This view include a many types of posts (text, image, video, gif).
<br><br>
<img src="images/social.png">

* You only need to include social view JS file in HTML page to use this view.

```html
<!-- Social JS file -->

<script type="text/javascript" src="assets/js/social.js"></script>
```


# Maps


## Vector Map

We used <a target="_blank" href="http://www.highcharts.com/maps/demo">Highmaps</a> library in this view.

<img src="images/vector_map.png">

* In order to use the features of this page all you need to do is to: 

  - Include the highmaps library in your HTML page.
  - define a container in the HTML page.
  - Initialize the map in JS. 

  as shown in the example.

```html
<!-- Map container -->

<div id="container"></div>

<!-- highmaps library -->

<script type="text/javascript" src="assets/vendors/highmaps/code/highmaps.js"></script>
<script type="text/javascript" src="assets/vendors/highmaps/code/modules/data.js"></script>
<script type="text/javascript" src="assets/vendors/highmaps/code/modules/exporting.js"></script>
<script type="text/javascript" src="assets/vendors/highmaps/code/custom/world.js"></script>

```

```javascript

  // Initiate the chart

$.getJSON('https://www.highcharts.com/samples/data/jsonp.php?filename=world-population-density.json&callback=?', function(data) {

$('#container').highcharts('Map', {
    title: {
      text: ''
    },
    mapNavigation: {
      enabled: true,
      buttonOptions: {
        verticalAlign: 'bottom'
      },
      enableMouseWheelZoom: false
    },
    colorAxis: {
      dataClasses: [{
        to: 100,
        color: '#67b2e4'
      }, {
        from: 100,
        to: 10000,
        color: '#999999'
      }],
      min: 1,
      max: 1000,
      type: 'logarithmic'
    },
    exporting: {
      buttons: [{
        symbol: '',
      }]
    },
    series: [{
      data: data,
      mapData: Highcharts.maps['custom/world'],
      joinBy: ['iso-a2', 'code'],
      name: 'Cumulative Sales',
      color: 'red',
      states: {
        hover: {
          color: '#3498db'
        }
      },
      tooltip: {
        valueSuffix: '0$'
      }
    }]
  });
});

```

## Google Map

This map created using <a href="https://developers.google.com/maps/documentation/javascript/tutorial" target="_blank">google maps javascript API</a>.

* All you need to do is to include blue dashboard's style file in addition to the google map style file and the google api library file.

<img src="images/google_map.png" />

```html
<!-- google maps Css file -->

<link type="text/css" rel="stylesheet" href="assets/css/google-map.css">

<!-- google api library -->

<script type="text/javascript" src="https://maps.googleapis.com/maps/api/js?key=AIzaSyB0bxmUytZ20M6YA2DA7auQPOB97kzjlHw&callback=initMap" async defer></script>

<script type="text/javascript" src="assets/js/google-maps.js"></script>

<!-- map container -->

<div id="map"></div>


```
### Map Options

* There are two required options for every map:
  - Center 
  - Zoom.

```javascript

// Map initialization 

map = new google.maps.Map(document.getElementById('map'), {
  center: {lat: -34.397, lng: 150.644},
  zoom: 8
});

```

* Zoom Levels
 - 1: World
 - 5: Landmass/continent
 - 10: City
 - 15: Streets
 - 20: Buildings

<img src="images/google_map_zoom.png"> 


# Invoice

Blue Dashboard include invoice view with save and print feature.

* All you have to do to use this feature is to include the blue dashboard style file and copy the source code to your HTML page.

<img src="images/invoice.png">
