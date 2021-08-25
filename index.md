---
layout: default
title: Ponyblod
---

  <style>
    .countup .countdown {
      text-align: center;
      margin-bottom: 20px;
    }
    .countup .countdown .timeel {
      display: inline-block;
      padding: 10px;
      background: #151515;
      margin: 0;
      color: white;
      min-width: 2.6rem;
      margin-left: 13px;
      border-radius: 10px 0 0 10px;
    }
    .countup .countdown span[class*="timeRef"] {
      border-radius: 0 10px 10px 0;
      margin-left: 0;
      background: #B5E853;
      color: black;
    }
  </style>

# Time since ponyblod was created
```html
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
```
 
 # Time until next bornhack
 
 ```html
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

  <script>
    window.onload = function() {
      // Month Day, Year Hour:Minute:Second, id-of-element-container
      countUpFromTime("Aug 25, 2021 13:37:00", 'countup1'); // ****** Change this line!
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
  </script>
  ```

