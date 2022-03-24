---
title: Termine
subtitle: Aktuelle Termine
comments: false
---

<termin></termin>

<script type="text/javascript">
jQuery('<div id="termin" style="font-size:70%;"></div>').insertBefore(jQuery('termin').first())
jQuery.get('https://eigenbaukombinat.de/api/kalender', function(resp) {
var json = '';
for(var i = 0; i < 13; i++){
json = json + resp[i].startdate + ' ' + resp[i].starttime + ' - ' +  resp[i].enddate + ' ' + resp[i].endtime + ' ' +  resp[i].summary+ '<br>'

  };
  jQuery('#termin').html('<span style="color:white; padding:3px 5px 3px 5px; border-radius:4px; display:inline-block;"><span id="termin">' + json + '</span></span>');
});
</script>

