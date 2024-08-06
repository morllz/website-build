---
author: Andrea Thum
date: 2015-09-20 12:02:53+00:00
draft: false
title: Unsere Veranstaltungen
type: page
url: /unsere-veranstaltungen/
---

<termin>
 <noscript><div id="spacestatus" style="font-size:100%;">
  <span style="color:#f2f2f2; background-color:#f0ad4e; padding:3px 5px 3px 5px; border-radius:4px;display:inline-block;">Dein Browser unterstütze kein JavaScript!</span>
  </div>
 </noscript>
</termin>  

Unsere Termine gibt es auch hier als [iCal](https://kalender.eigenbaukombinat.de/public/public.ics)  
  


<script type="text/javascript">
jQuery('<div id="termin" ></div>').insertBefore(jQuery('termin').first())
jQuery.get('https://eigenbaukombinat.de/api/kalender', function(resp) {
var json = '';
for(var i = 0; i < 25; i++){
  //url verlinken, wenn vorhanden
  if (resp[i].url) {
    summary = '<a href="'+resp[i].url+'">'+resp[i].summary+'</a>';
  } else {
    summary = resp[i].summary;
  }
  //enddate nur anzeigen, wenn != startdate
  if (resp[i].startdate != resp[i].enddate) {
    enddate = ' '+resp[i].enddate;
  } else {
    enddate = '';
  }
json = json + '' + resp[i].startdate + ' ' + resp[i].starttime + ' - ' +  resp[i].enddate + ' ' + resp[i].endtime + ' ' +  summary + '</br>'

  };
  jQuery('#termin').html('<span padding:3px 5px 3px 5px; border-radius:4px; display:inline-block;"><span id="termin">' + json + '</span></span>');
});
</script>
