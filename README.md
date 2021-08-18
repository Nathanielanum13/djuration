# Installation

Djuration is built to provide frequently used time functions and properties at your disposal

You can add Djuration to your project using 3 different approaches

1. Import it using [script](#script) `<script></script>` on the page
2. Download the JavaScript file from [GIT](https://gitlab.com/nathanielanum13/djuration.git) and import it
3. Install it using [npm](#npm)

## Release Notes

Current release version `1.0.0`

Detailed release notes for each version are available on [GitHub](https://gitlab.com/nathanielanum13/djuration.git).

## script

You can use Djuration with:

```html
<script src="djuration.js"></script>
```

## npm

Use npm to install the Djuration by:

```bash
$ npm install djuration
```

## methods, properties and usage

Djuration is a class based library that accepts one constructor argument of type number. i.e duration `in milliseconds`

* methods

  > **toMilliseconds()**
  >

  ```javascript
    /**
     * @param {number} seconds
     * `Converts seconds to milliseconds`
     */
  ```
  > **formatInSecond()**
  >

  ```javascript
    /**
     * @param {number} num
     * `Converts milliseconds to a formated second. e.g 1 second`
     */
  ```
  > **formatInMinute()**
  >

  ```javascript
    /**
     * @param {number} num
     * `Converts milliseconds to a formated minute. e.g 2 minutes`
     */
  ```
  > **formatInHour()**
  >

  ```javascript
    /**
     * @param {number} num
     * `Converts milliseconds to a formated hour. e.g 1 hour`
     */
  ```
  > **formatInDay()**
  >

  ```javascript
    /**
     * @param {number} num
     * `Converts milliseconds to a formated day. e.g 21 days`
     */
  ```
  > **formatInWeek()**
  >

  ```javascript
    /**
     * @param {number} num
     * `Converts milliseconds to a formated week. e.g 2 weeks`
     */
  ```
  > **formatAll(separator)**
  >

  ```javascript
    /**
     * @param {string} separator
     * `Converts milliseconds to e.g 1 week 3 days 11 hours`
     */
  ```
* getters

  > **toSeconds**
  > `Returns an object with class constructor argument in seconds and the remaining in seconds`
  >

  > **toWeeks**
  > `Returns an object with class constructor argument in weeks and the remaining in seconds`
  >

  > **toDays**
  > `Returns an object with class constructor argument in days and the remaining value in seconds`
  >

  > **toHours**
  > `Returns an object with class constructor argument in hours and the remaining in seconds`
  >

  > **toMinutes**
  > `Returns an object with class constructor argument in minutes and the remaining in seconds`
  >

  > **getTrans**
  > `Outputs Translations for Duration formats`
  >
* setters

  > **setWeekTrans(preferredTrans)**
  >

  ```javascript
    /**
     * @param {string} preferredTrans
     */
  ```
  > **setDayTrans(preferredTrans)**
  >

  ```javascript
    /**
     * @param {string} preferredTrans
     */
  ```
  > **setHourTrans(preferredTrans)**
  >

  ```javascript
    /**
     * @param {string} preferredTrans
     */
  ```
  > **setMinuteTrans(preferredTrans)**
  >

  ```javascript
    /**
     * @param {string} preferredTrans
     */
  ```
  > **setSecondTrans(preferredTrans)**
  >

  ```javascript
    /**
     * @param {string} preferredTrans
     */
  ```
* usage

  > Step 1 :: import the file in your project
  >

  ```js
  import Duration from "djuration"
  ```
  > Step 2 :: Example
  >

  ```javascript
  const inProgress = new Date("Tue Aug 17 2021 07:01:05")
  const done = new Date("Sun Aug 29 2021 01:15:23")

  const timeTaken = done - inProgress // in milliseconds
  const duration = new Duration(timeTaken)

  console.log(duration.formatAll(" "))
  onsole.log(duration.formatInDay(/* Optional param */))

  // Changing Translations
  // i.e week = wk, hour = hr, minute = min, second = sec

  duration.setWeekTrans = "wk" // Singular
  duration.setHourTrans = "hr" // Singular
  duration.setMinuteTrans = "min" // Singular
  duration.setSecondTrans = "sec" // Singular

  console.log(duration.formatAll(" - "))


  ```
  **Output**

  ```bash
  1 week 4 days 18 hours 14 minutes 18 seconds
  11 days

  #after translations have been set

  1 wk - 4 days - 18 hrs - 14 mins - 18 secs

  ```
