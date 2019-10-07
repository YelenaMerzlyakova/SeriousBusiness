# [SeriousBusiness]()

First real Javascript/Jquery exercise.

## Objectives

Learn how to use if statements and combine them 

- [X] When you load the page:
    - [X] Check the day
    - [X] Check the time
    - [X] Compare it to the business hours
    - [X] Declare if the business is open
    

## BONUS Objective

- [X] Add a live updating clock of the current time (digital) :clock9:


## BONUS Objectives to ADD! 
- [ ] Add a button "Close early"
- [ ] When you click this button, the current day's business hours end at the current time in the table


## Result 

![page](https://github.com/YelenaMerzlyakova/SeriousBusiness/blob/master/business.png)


## Code 

Here is the code that I used to show the time. It's pretty self explanatory.

``` Javascript

    function showTime(){
    var date = new Date();
    var h = date.getHours(); // 0 - 23
    var m = date.getMinutes(); // 0 - 59
    var s = date.getSeconds(); // 0 - 59
    var session = "AM";
    
    if(h == 0){
        h = 12;
    }
    
    if(h > 12){
        h = h - 12;
        session = "PM";
    }
    
    h = (h < 10) ? "0" + h : h;
    m = (m < 10) ? "0" + m : m;
    s = (s < 10) ? "0" + s : s;
    
    var time = h + ":" + m + ":" + s + " " + session;
    document.getElementById("MyClockDisplay").innerText = time;
    document.getElementById("MyClockDisplay").textContent = time;
    
    setTimeout(showTime, 1000);
    
}


