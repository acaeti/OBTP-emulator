# README

The Cisco TelePresence One Button to Push (OBTP) emulator is a simple HTML file that can be opened locally in a browser and used to "push" a meeting into a Cisco TelePresence endpoint, emulating the "push" an endpoint would receive from Cisco TelePresence Management Suite (TMS).

## Usage

The HTML file asks for the Cisco TelePresence end-point IP address, the desired meeting title, and the destination address (e.g. SIP URI).  Upon clicking "Set the Meeting" a JavaScript xmlhttprequest fires to perform an HTTP POST to the target device, and the user will be prompted to enter admin credentials (in a standard HTTP Basic Authentication dialog).  Unfortunately credential entry in the form is not supported due to a lack of CORS configuration support on Cisco TelePresence end-points.

Caution is advised when using the emulator with endpoints already setup for OBTP as it may overwrite other meetings already in the endpoint's internal "booking list" - then again, if there is already OBTP you likely don't need to use this emulator.

## Supported Cisco TelePresence devices

The HTML file has only undergone limited testing with:

* Cisco DX-80 running CE 9.1.4
* Cisco EX-90 running TC 7.3.9

However, it should work with essentially all current endpoints and software.  Devices are supported whether standalone, registered to Cisco VCS or Expressway, registered to Cisco Unified Communications Manager, or registered to other 3rd party call control platforms.

**Important note:** There is no support for devices registered to Cisco Spark, due to how Cisco Spark changes web services API authentication.

## Hard coded meeting variables

A number of variables are hard-coded in the HTML page, but could easily be changed in a text editor.  They include:

* The "join early" time (StartTimeBuffer) is set to 300 seconds (5 minutes)
* The meeting start time is automatically set to five (5) minutes from the current time
* The meeting end time is automatically set to fifteen (15) minutes from the current time

However, the date range picker does allow you to set your own meeting times if the defaults don't suit.

## Notes

Due to browser JavaScript sandboxing and lack of CORS support on Cisco TelePresence, only limited error detection is possible.  Sorry!

## Built With

* The web layout is based on the ["Stylish Portfolio" theme](https://startbootstrap.com/template-overviews/stylish-portfolio/) from [Start Bootstrap](https://startbootstrap.com/)
* [Bootstrap](http://www.getbootstrap.com/), Copyright (c) 2011-2014 Twitter, Inc. [http://www.getbootstrap.com](http://www.getbootstrap.com/)
* [Font Awesome](http://fontawesome.io/) by Dave Gandy - [http://fontawesome.io](http://fontawesome.io)
* Background image courtesy of [Cisco Systems, Inc.](http://www.cisco.com), Unauthorized use not permitted.
* [Moment.js](http://momentjs.com) - [http://momentjs.com](http://momentjs.com/)
* [Daterangepicker](http://www.daterangepicker.com) by Dan Grossman - [http://www.daterangepicker.com/](http://www.daterangepicker.com/)
* [jQuery](http://jquery.org) - [http://jquery.org](http://jquery.org)

## Authors

* Nick Mueller, [CDW](http://www.cdw.com)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

## Acknowledgements

* Hat tip to James Adams, CDW, for challenging me with the idea
* Hat tip to David Bruun-Lie, Cisco Systems, for some code pointers