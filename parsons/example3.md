<div id="trial-sortableTrash" class="sortable-code"></div> 
<div id="trial-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="trial-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="trial-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "def factorial(n):\n" +
    "    if n == 0:\n" +
    "        return 1\n" +
    "    else:\n" +
    "        return n * factorial(n - 1)\n" +
    "number = int(input(&quot;Enter a number: &quot;))\n" +
    "result = factorial(number)\n" +
    "print(&quot;The factorial of&quot;, number, &quot;is&quot;, result)";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "trial-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#trial-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#trial-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
