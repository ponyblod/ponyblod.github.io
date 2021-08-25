---
layout: default
---

<style>
  .countup {
    text-align: center;
    margin-bottom: 20px;
  }
  .countup .timeel {
    display: inline-block;
    padding: 10px;
    background: #151515;
    margin: 0;
    color: white;
    min-width: 2.6rem;
    margin-left: 13px;
    border-radius: 10px 0 0 10px;
  }
  .countup span[class*="timeRef"] {
    border-radius: 0 10px 10px 0;
    margin-left: 0;
    background: #B5E853;
    color: black;
  }
  .countdown {
    text-align: center;
    margin-bottom: 20px;
  }
  .countdown .timeel {
    display: inline-block;
    padding: 10px;
    background: #151515;
    margin: 0;
    color: white;
    min-width: 2.6rem;
    margin-left: 13px;
    border-radius: 10px 0 0 10px;
  }
  .countdown span[class*="timeRef"] {
    border-radius: 0 10px 10px 0;
    margin-left: 0;
    background: #B5E853;
    color: black;
  }
</style>

# Time since ponyblod was created [25 Aug, 2021 13:37]

<div class="countup" id="countup1">
  <span class="timeel days">00</span>
  <span class="timeel timeRefDays">days</span>
  <span class="timeel hours">00</span>
  <span class="timeel timeRefHours">hours</span>
  <span class="timeel minutes">00</span>
  <span class="timeel timeRefMinutes">minutes</span>
  <span class="timeel seconds">00</span>
  <span class="timeel timeRefSeconds">seconds</span>
</div>

 
# Time until next bornhack [3 Aug, 2022 12:00]
 

<div class="countdown" id="countdown1">
  <span class="timeel days">00</span>
  <span class="timeel timeRefDays">days</span>
  <span class="timeel hours">00</span>
  <span class="timeel timeRefHours">hours</span>
  <span class="timeel minutes">00</span>
  <span class="timeel timeRefMinutes">minutes</span>
  <span class="timeel seconds">00</span>
  <span class="timeel timeRefSeconds">seconds</span>
</div>

<div class="posts">
  {% for post in site.posts %}
    <article class="post">

      <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>

      <div class="entry">
        {{ post.excerpt }}
      </div>

      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
    </article>
  {% endfor %}
</div>

<script>
  window.onload = function() {
    // Month Day, Year Hour:Minute:Second, id-of-element-container
    countUpFromTime("Aug 25, 2021 13:37:00", 'countup1');
      // Month Day, Year Hour:Minute:Second, id-of-element-container
    countDownToTime("Aug 3, 2022 12:00:00", 'countdown1');
  };
  function countUpFromTime(countFrom, id) {
    countFrom = new Date(countFrom).getTime();
    var now = new Date(),
        countFrom = new Date(countFrom),
        timeDifference = (now - countFrom);

    var secondsInADay = 60 * 60 * 1000 * 24,
        secondsInAHour = 60 * 60 * 1000;

    days = Math.floor(timeDifference / (secondsInADay) * 1);
    hours = Math.floor((timeDifference % (secondsInADay)) / (secondsInAHour) * 1);
    mins = Math.floor(((timeDifference % (secondsInADay)) % (secondsInAHour)) / (60 * 1000) * 1);
    secs = Math.floor((((timeDifference % (secondsInADay)) % (secondsInAHour)) % (60 * 1000)) / 1000 * 1);

    var idEl = document.getElementById(id);
    idEl.getElementsByClassName('days')[0].innerHTML = days;
    idEl.getElementsByClassName('hours')[0].innerHTML = hours;
    idEl.getElementsByClassName('minutes')[0].innerHTML = mins;
    idEl.getElementsByClassName('seconds')[0].innerHTML = secs;

    clearTimeout(countUpFromTime.interval);
    countUpFromTime.interval = setTimeout(function(){ countUpFromTime(countFrom, id); }, 1000);
  }
  function countDownToTime(countTo, id) {
    countTo = new Date(countTo).getTime();
    var now = new Date(),
        countTo = new Date(countTo),
        timeDifference = (countTo - now);
        
    var secondsInADay = 60 * 60 * 1000 * 24,
        secondsInAHour = 60 * 60 * 1000;

    days = Math.floor(timeDifference / (secondsInADay) * 1);
    hours = Math.floor((timeDifference % (secondsInADay)) / (secondsInAHour) * 1);
    mins = Math.floor(((timeDifference % (secondsInADay)) % (secondsInAHour)) / (60 * 1000) * 1);
    secs = Math.floor((((timeDifference % (secondsInADay)) % (secondsInAHour)) % (60 * 1000)) / 1000 * 1);

    var idEl = document.getElementById(id);
    idEl.getElementsByClassName('days')[0].innerHTML = days;
    idEl.getElementsByClassName('hours')[0].innerHTML = hours;
    idEl.getElementsByClassName('minutes')[0].innerHTML = mins;
    idEl.getElementsByClassName('seconds')[0].innerHTML = secs;

    clearTimeout(countDownToTime.interval);
    countDownToTime.interval = setTimeout(function(){ countDownToTime(countTo, id); },1000);
  }
</script>
