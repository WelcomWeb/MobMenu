# MobMenu, easy to use mobile menu

## About
We struggled through a lot of projects with different ways of creating mobile menus that works as we wanted. We decided to create a way of doing it, this is it.

## Dependencies
None

## Browser support
The library is tested in (and on):

* Android chrome & browser
* iPhone Safari
* Windows Mobile 8.1 - IE

## Usage
MobMenu needs minimal setup - the minimum amount of CSS, HTML and JavaScript is as follows;

### HTML
	<div class="mobile-content">
		<div class="ui-block"></div>
		<header>
			<div class="desktop-header">
				{DESKTOP HEADER}
			</div>
			<div class="mobile-header">
				<div id="mobile-nav-toggle"></div>
				{MOBILE HEADER}
			</div>
		</header>
		<div class="page-container">
			{PAGE HTML}
		</div>
	</div>
	<div class="mobile-left">
		{MENU HTML}
	</div>

### CSS
	body.open-left{
	  overflow: hidden;
	}
	  body.open-left .mobile-content{
	  	margin-left:75%;
	  	position: fixed;
	  }
	  body.open-left .mobile-left{
	  	overflow: auto;
	  	left:0px;
	  }
	  body.open-left .ui-block{
	  	position: absolute;
	  	left:0px;
	  	right:0px;
	  	top:0px;
	  	bottom:0px;
	  	z-index: 999999;
	  }
	
	/* LEFT SECTION (HIDDEN ON START) */
	.mobile-left{
	  position: fixed;
	  overflow-y:auto;
	  top:0px;
	  width: 75%;
	  height: 100%;
	}
	.mobile-left{
	  left:-75%;
	  transition: left 0.5s;
	  background-color: #EEE;
	}
	.mobile-content{
	  transition: margin-left 0.5s;
	  width:100%;
	  position: relative;
	}

#### JavaScript
	document.querySelector('.ui-block').addEventListener('click', function (e) {
	  e.stopPropagation();
	  e.preventDefault();
	  document.body.className = document.body.className.replace('open-left', '');
	});
	//OPEN MOBILE MENU
	var menu_toggle_button = document.getElementById('mobile-nav-toggle');
	menu_toggle_button.onclick = function() {
	  document.querySelector('body').classList.add('open-left');
	}

## Demo
A more extensive demo is available at [http://welcomweb.se/MobMenu](http://welcomweb.se/MobMenu).

## License
Swipr is released under [LGPL 3](https://www.gnu.org/copyleft/lesser.html).


Happy coding!

[![githalytics.com alpha](https://cruel-carlota.pagodabox.com/64a45e5f0863b6ef44cdfbf328cb930a "githalytics.com")](http://githalytics.com/WelcomWeb/MobMenu)
