# Introduction

Welcome to the Blue Dashboard! You can use our dashboard to manage your business easily, where you can get information and statistics through charts, tables, modals and more.

Blue Dashboard is built using modern Bootstrap according to high standards in UX/UI design.

This Documentation will help you to use the dashboard effectively.


# Calendar

Blue Dashboard include a JavaScript event calendar using <a target="_blank" href="https://fullcalendar.io/">fullcalendar</a> library.
We customize the UI design for this view and its modals to be user friendly and easy to use. 

<img src="images/Pasted image at 2017_03_23 12_49 PM.png">

## Calendar Lib

```HTML
<script src="assets/js/calendar.js"></script>
```

## Dependencies

```HTML
<link href="assets/vendors/calendar/calendar_theme.css" rel="stylesheet" />
<link href='assets/vendors/calendar/fullcalendar.css' rel='stylesheet' />
<link href="assets/vendors/calendar/fullcalendar.print.css" rel='stylesheet' media='print' />
<script src="assets/vendors/calendar/lib/moment.min.js"></script>
<script src="assets/vendors/calendar/fullcalendar.min.js"></script>
```

## HTML Source

Include this HTML source to your page.

```HTML
<div id='calendar'></div>
```


# Colors

## Primary

<img src="images/primary.png">

## Info

<img src="images/info.png">

## Success

<img src="images/danger.png">

## Warning

<img src="images/warning.png">

## Danger

<img src="images/danger.png">

## Default

<img src="images/default.png">


# Icons

Blue Dashboard include the popular font icons libraries, <a target href="http://fontawesome.io/">fontawesome</a> and <a href="http://getbootstrap.com/components/">glyphicons</a>.

<img src="images/icons.png">

## Fontawesome

Just include the icon class like the HTML sample to use it in the dashboard.


```HTML
<link type="text/css" href="assets/vendors/font-awesome/css/font-awesome.min.css" rel="stylesheet" />

<i class="fa fa-user-circle" aria-hidden="true"></i>
```

## Glyphicons
Just include the icon class like the HTML sample to use it in the dashboard.

```HTML
<link type="text/css" href="assets/vendors/bootstrap/css/bootstrap.min.css" rel="stylesheet">

<span class="glyphicon glyphicon-asterisk"></span>
```


# Tables

## Basic Tables

Blue Dashboard use <a target="_blank" href="http://getbootstrap.com/css/#tables">Bootstrap</a> tables with custom design.
You can use any custom class with <code>table</code> tag to get the style.

### Users Table Style

You juat need to add <code>.users-table</code> class to the table tag to git this style.

<img src="images/users_table.png"/>

```HTML
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

```HTML
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

You can change the table head color using add any color class (eg:<code>.info-mid</code>).

## Data Tables

Blue Dashboard use <a target="_blank" href="https://datatables.net/">DataTables</a> plug-in with custom design.
This plug-in include many features (search, sort, pagination, child rows, copy, export and more).

<aside class="notice">
You can read DataTables <a href="https://datatables.net/examples/index">documentation</a> to learn about plug-in options and features.
</aside>

```HTML
<script type="text/javascript" src="assets/vendors/datatables/media/js/jquery.dataTables.min.js"></script>
<script type="text/javascript" src="assets/vendors/datatables/extensions/Buttons/js/dataTables.buttons.min.js"></script>
<script type="text/javascript" src="assets/vendors/datatables/extensions/Buttons/js/buttons.html5.min.js"></script>
<script type="text/javascript" src="assets/js/data_table.js"></script>
```


# App Views

## Account Management

You can manage your personal banking accounts using this view.
<br>
<br>
<img src="images/account_managment.png">

### Account Management Lib

```HTML
<script type="text/javascript" src="assets/js/account-manager.js"></script>
```

### Date Picker

```HTML
<link type="text/css" rel="stylesheet" type="text/css" href="assets/vendors/datepickers/daterangepicker.css" />
<link type="text/css" rel="stylesheet" type="text/css" href="assets/vendors/air-datepicker/css/datepicker.min.css">
<script type="text/javascript" src="assets/vendors/air-datepicker/js/datepicker.min.js"></script>
<script type="text/javascript" src="assets/vendors/air-datepicker/js/datepicker.en.js"></script>
```

### Chart

```HTML
<script type="text/javascript" src="assets/vendors/highcharts/highcharts.js"></script>
<script type="text/javascript" src="assets/vendors/highcharts/modules/data.js"></script>
<script type="text/javascript" src="assets/vendors/highcharts/modules/exporting.js"></script>
```

### Data Table

```HTML
<script type="text/javascript" src="assets/vendors/datatables/media/js/jquery.dataTables.min.js"></script>
<script type="text/javascript" src="assets/vendors/datatables/extensions/Buttons/js/dataTables.buttons.min.js"></script>
<script type="text/javascript" src="assets/vendors/datatables/extensions/Buttons/js/buttons.html5.min.js"></script>
```

## Landing Page

This view include five main sections : 
<br><br>
<img src="images/landing_page.png">

### Showcase Video

### Features

Using <a target="_blank" href="https://owlcarousel2.github.io/OwlCarousel2/">OWL Carousel</a> Library.

```HTML
    <link rel="stylesheet" href="assets/vendors/owlcarousel/owl.carousel.min.css">
    <link rel="stylesheet" href="assets/vendors/owlcarousel/owl.carousel.css">
    <link rel="stylesheet" href="assets/vendors/owlcarousel/owl.theme.default.min.css">
    <script src="assets/vendors/owlcarousel/highlight.js"></script>
    <script src="assets/vendors/owlcarousel/app.js"></script>
    <script src="assets/vendors/owlcarousel/owl.carousel.js"></script>
    <script src="assets/vendors/owlcarousel/owl.carousel.min.js"></script>
```

### Technologies

### Our Team

### Pricing

### Map

Using Google Map API.

```HTML
<script src="assets/js/landing_map.js"></script>
<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyB0bxmUytZ20M6YA2DA7auQPOB97kzjlHw&callback=initMap" async defer></script>
```

## Chat View

Blue Dashboard include a full chat application view with many features like create a new channels or start a new direct conversation with any user, also you can send multi types of messages (text, image, youtube video..)

<img src="images/chat_view.png">

### Create Channel Modal

<img src="images/creat_channel.png">

### Direct Messages Modal

<img src="images/direct_message.png">

```HTML
 <script src="assets/js/chat.js"></script>
```

## Social

You can use Blue Dashboard social view for any social timeline. This view include a multi types of posts (text, image, video, gif).
<br><br>
<img src="images/social.png">

### Social Lib

You only need to include social view js file in HTML page to use this view.

```HTML
<script type="text/javascript" src="assets/js/social.js"></script>
```


# Maps


## Vector Map

We use <a target="_blank" href="http://www.highcharts.com/maps/demo">Highmaps</a> library in this view.

<img src="images/vector_map.png">

```HTML
<div id="container" class="map-layout"></div>

<script type="text/javascript" src="assets/js/map.js"></script>
<script type="text/javascript" src="assets/vendors/highmaps/code/highmaps.js"></script>
<script type="text/javascript" src="assets/vendors/highmaps/code/modules/data.js"></script>
<script type="text/javascript" src="assets/vendors/highmaps/code/modules/exporting.js"></script>
<script type="text/javascript" src="assets/vendors/highmaps/code/custom/world.js"></script>
```

## Google Map

This map created using <a href="https://developers.google.com/maps/documentation/javascript/tutorial" target="_blank">google maps javascript API</a>.

<img src="images/google_map.png" />

```HTML
<link type="text/css" rel="stylesheet" href="assets/css/google-map.css">

<div id="map"></div>

<script type="text/javascript" src="https://maps.googleapis.com/maps/api/js?key=AIzaSyB0bxmUytZ20M6YA2DA7auQPOB97kzjlHw&callback=initMap" async defer></script>
<script type="text/javascript" src="assets/js/google-maps.js"></script>
```
### Map Options
There are two required options for every map: center and zoom.

```javascript
map = new google.maps.Map(document.getElementById('map'), {
  center: {lat: -34.397, lng: 150.644},
  zoom: 8
});
```

### Zoom Levels

#### 1: World
#### 5: Landmass/continent
#### 10: City
#### 15: Streets
#### 20: Buildings

<img src="images/google_map_zoom.png"> 


# Invoice

Blue Dashboard include invoice view with save and print feature.

<img src="images/invoice.png">