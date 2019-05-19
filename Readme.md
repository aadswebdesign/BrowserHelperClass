
<h2>Subject: BrowserHelper</h2>
<p>Based on and Credits to: <span>james2doyle/getBrowser.php</span>  </p>

<h3>Updates</h3>
<table>
   <thead><td>No</td><td>Date</td><td>Description</td></thead>
   <tr><td>001</td><td>19-05-2019</td><td>added platforms "iPad" and "iPhone(just I'm unable to test on iPhone but I guess it's right?)" </td></tr>
   <tr><td>002</td><td>19-05-2019</td><td>added user browser "CriOS (Chrome on Ipad)" </td></tr>
</table>

<h3>Summery:</h3>
<ul>
   <li>Language:<span>PHP</span></li>
   <li>Version:<span>5+</span></li>
   <li>Developed on:<span>7.3</span></li>
   <li>Purpose:<span> A helper class to obtain info and to perform actions upon the user's browser</span></li>
</ul>

<h3 style="margin-bottom:-15px">Capabilities:</h3>
<ul>
   <li>Obtain and print the user's user agent info:<span style="color: blue; font-size: 0.9em"><strong>getBrowserInfo()</strong></span>
   <h4 style="margin-top:0 ; margin-botom:0">Options</h4>
   <ul style="margin-top:0">
        <li style="padding-top:-20px">Printing in HTML:<span style="color: blue; font-size: 0.9em"><strong>setUseHtml(true)</strong></span><div>This is an ul(class 'browser-details-ul') / li(class 'browser-detail-li') setup!</div></li>   
        <li>Adding a parent element:<span style="color: blue; font-size: 0.9em">eg: <strong>setWrapper('div')</strong></span></li>   
        <li>Adding attributes on that element:<span style="color: blue;  font-size: 0.9em">eq: <strong>setAttribute('class="foo" style="css:rules"')</strong></span></li>   
   </ul>
   </li>
   <li style="margin-top:0;">Perform actions based on user's platfom:<span style="color: blue;  font-size: 0.9em">eg:<strong>IsPlatform('Mac')</strong></span></li>
   <li>Perform actions based on user's browser:<span style="color: blue;  font-size: 0.9em">eg:<strong>IsUserBrowser('Safari')</strong></span></li>
   <li>Perform actions based on user's browser & version number 'this is with built in comparison':<span style="color: blue;  font-size: 0.9em">eg:<strong>IsVersion('Equal', '10.0')</strong></span>
   <div>The options are:</div>
   <ul style="color:olivedrab">
   <li>Equal</li>
   <li>NotEqual</li>
   <li>GreaterThan</li>
   <li>LessThan</li>
   <li>GreaterThanOrEqualTo</li>
   <li>LessThanOrEqualTo</li>
   </ul>
   </li>
</ul> 

<h3>Howto:</h3>

`<?php`
```
require_once('path/to/BrowserHelper.php');
// in case of namespaced

use path\to\BrowserHelper;


//in a function eg:
function print_useragent(){
    $browser = new BrowserHelper();
    $this->_browser = new BrowserHelper();
        // 
        if($browser->IsPlatform('Mac')): 
            // your actions for this platform
        else:
            // your actions for the other platforms
        endif;
        
        if($browser->IsUserBrowser('Chrome')): 
            // your actions for this browser
        else:
            // your actions for the other browsers
        endif;
        
        if($browser->IsUserBrowser('Chrome') and $browser->IsVersion('LessThanOrEqualTo', '70.0')): 
           // your actions for this browser and depending on the version number
        // if more comparisons
        elseif($browser->IsUserBrowser('Chrome') and $browser->IsVersion('LessThanOrEqualTo', '60.0')):   
            //second step, your actions for this browser and depending on the version number
        else:
           // your actions for the other browsers and version numbers
        endif;
    /**
     * this options are chainable!
    */
    //if you want it printed in html
    $browser->setUseHtml(true);
    //if you want a parent element eg:
    $browser->setWrapper('div');
    //if you want add attributes to the parent element eg:
    $browser->setAttribute('class="foo" style="css:rules"')
    //echo or return  $browser->getBrowserInfo();
}
    
// in a class
protected $_browser;
// within a class function eg:
public function __construct(){
    $this->_browser = new BrowserHelper();
    // 
    if($this->_browser->IsPlatform('Mac')): 
        // your actions for this platform
    else:
        // your actions for the other platforms
    endif;
    
    if($this->_browser->IsUserBrowser('Chrome')): 
        // your actions for this browser
    else:
        // your actions for the other browsers
    endif;
    
    if($this->_browser->IsUserBrowser('Chrome') and $this->_browser->IsVersion('LessThanOrEqualTo', '70.0')): 
       // your actions for this browser and depending on the version number
    // if more comparisons
    elseif($this->_browser->IsUserBrowser('Chrome') and $this->_browser->IsVersion('LessThanOrEqualTo', '60.0')):   
       //second step, your actions for this browser and depending on the version number
    else:
       // your actions for the other browsers and version numbers
    endif;
}

public function print_useragent(){
    /**
     * this options are chainable!
    */
    //if you want it printed in html
    $this->_browser->setUseHtml(true);
    //if you want a parent element eg:
    $this->_browser->setWrapper('div');
    //if you want add attributes to the parent element eg:
    $this->_browser->setAttribute('class="foo" style="css:rules"')
    //echo or return  $this->_browser->getBrowserInfo();
    
}
```

<h4 style="margin-bottom:-15px">About me.</h4>
<p>I'm not a php expert and just have a basic knowledge about it. I usually get there by looking up examples, making mistakes, learning and above all with persistence. Therefor constructive critics are alway welcome.
 </p>
 
<h5 style="margin-top:-10px;margin-bottom:-15px">My website: https://www.aadswebdesign.nl</h5> 
<h5 style="margin-bottom:-15px">In progress.</h5>
<p>
This site is in progress and there is still a lot to be done. Because I have limited time for that, the progrees is at a slow pace. At the first page I have an html print of browserinfo. 
<?p>
 
 
