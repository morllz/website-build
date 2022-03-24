###
<space></space>

<noscript><div id="spacestatus" style="font-size:100%;"><span style="color:#f2f2f2; background-color:#f0ad4e; padding:3px 5px 3px 5px; border-radius:4px;display:inline-block;">Your browser does not support JavaScript!</span></div>
</noscript> 

<script type="text/javascript">
jQuery('<div id="spacestatus" style="font-size:100%;"></div><div style="font-size: 100%; margin-top: 0.5ex; margin-bottom: 2.5ex;" id="spacestatus_sm"></div>').insertBefore(jQuery('space').first())
jQuery.get('https://eigenbaukombinat.de/status/status.json?' + jQuery.now(), function(resp) {

if (resp['state']['open']) {
   jQuery('#spacestatus').html('<span style="color:#f2f2f2; background-color:#5cb85c; padding:3px 5px 3px 5px; border-radius:4px; display:inline-block;">Eigenbaukombinat is <span id="howlong"></span> open,   <a href="/anpassung-der-verhaltensregeln/" style="color:#5c5cb8">Anmelde-, Verhaltens- und Hygieneregeln beachten</a>!</span>');

jQuery.get('https://eigenbaukombinat.de/status/openuntil.json?' + jQuery.now(), function(resp) {
  if (resp['closetime'] != null) {
      jQuery('#howlong').html(' until '+ 
resp['closetime'] +' o\'clock ');
  }
 });
 } else {
    jQuery('#spacestatus').html('<span style="color:#f2f2f2; background-color:#f0ad4e; padding:3px 5px 3px 5px; border-radius:4px;display:inline-block;">Eigenbaukombinat is closed.</span>');
};
});
</script>
