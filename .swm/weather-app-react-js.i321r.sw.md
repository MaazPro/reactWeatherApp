---
id: i321r
title: Weather App React Js
file_version: 1.1.2
app_version: 1.5.5
---

**Connection with Api in App.js**<br/>
\- Imports the useState react hook from react library.<br/>
\- This hook allows to track state in the newly released function component by react.<br/>
\- Imports axios an HTTP client for the browser which runs on the client side using XMLHttpRequests.<br/>
\- The state below takes in 2 values date and `setData`<swm-token data-swm-token=":src/App.js:6:7:7:`  const [data, setData] = useState({})`"/>.<br/>
\- Data is the value passed to it.<br/>
\- setData is the function that is used to change the state of the hook or the value of the hook.<br/>
\- The state below takes in 2 values location and setLocation.<br/>
\- location is the value passed to it.<br/>
\- setLocation is the function that is used to change the state of the hook or the value of the hook.<br/>
\- This hook will grab the location value passed to it by the input element.<br/>
\- This constant is the url value that is used to fetch data from the api.<br/>
\- String literals are used in-order to pass values to the url by variable value.<br/>
\- The `searchLocation`<swm-token data-swm-token=":src/App.js:26:4:4:`          onKeyPress={searchLocation}`"/> function is binded to the ”enter” key event.<br/>
\- axios is used to fetch data and promise is used to capture and display in this respect the data is displayed in console for testing purpose. Previously defined url is used to pass the value to axios.<br/>
\-By resetting the location value to non it clears the input field.

<br/>

**Page Structure**<br/>

\- The div with the `className`<swm-token data-swm-token=":src/App.js:21:4:4:`    &lt;div className=&quot;app&quot;&gt;`"/> of “app” is the root div of the page which hold all the elements used in this project.<br/>
\- The div below with the `className`<swm-token data-swm-token=":src/App.js:22:4:4:`      &lt;div className=&quot;search&quot;&gt;`"/> of “search” holds the input field element which is used to insert the data for the search query.<br/>
\-The div with the `className`<swm-token data-swm-token=":src/App.js:30:4:4:`     &lt;div className=&#39;container&#39;&gt;`"/> of “container” is wrapper div that holds the elements that are used to display data on the front end.<br/>
\- The page is divided in to two portions top and bottom.<br/>
\-The div with `className`<swm-token data-swm-token=":src/App.js:32:4:4:`      &lt;div className=&#39;top&#39;&gt;`"/> of “top” hold the div that displays the location inserted by the user.<br/>
\-The div with `className`<swm-token data-swm-token=":src/App.js:36:4:4:`        &lt;div className=&#39;temp&#39;&gt;`"/> of “temp” that displays the temperature from the Api.<br/>
\-The div with `className`<swm-token data-swm-token=":src/App.js:39:4:4:`        &lt;div className=&#39;description&#39; &gt;`"/> of “description” is the div that is rotated to 279 degrees which will display the description of the weather fetched from the Api.<br/>
\-The div with `className`<swm-token data-swm-token=":src/App.js:44:4:4:`            &lt;div className= &#39;bottom&#39;&gt;`"/> of “bottom” is the wrapper div which holds the elements that are displayed at the bottom of the page.<br/>
\-The div with `className`<swm-token data-swm-token=":src/App.js:45:4:4:`            &lt;div className=&#39;feels&#39;&gt;`"/> of “feels” displays the feels like value which is fetched from the Api.<br/>
\- It holds 1 child element “<p></p>” that will display the fetched value.<br/>
\-The div with className of “humidity” displays the humidity value which will be fetched from the Api. - It holds 1 child element “<p></p>” that displays the fetched value.<br/>
\-The div with className of “wind” that displays the wind speed value which will be fetched from the Api. - It holds 1 child element “<p></p>” that displays the fetched value.

<!-- empty line --><br/>

<!-- empty line --><br/>
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/App.js
```javascript
20       return (
21         <div className="app">
22           <div className="search">
23           <input
24               value={location}
25               onChange={event => setLocation(event.target.value)}
26               onKeyPress={searchLocation}
27               placeholder='Enter Location'
28               type="text" />
29           </div>
30          <div className='container'>
31           
32           <div className='top'>
33             <div className='location'>
34               <p>{data.name}</p>
35             </div>
36             <div className='temp'>
37               {data.main ? <h1>{data.main.temp.toFixed()}°C</h1> : null}
38             </div>
39             <div className='description' >
40             {data.weather ? <p>{data.weather[0].main}</p> : null}
41             </div>
42           </div>
43           {data.name != undefined && 
44                 <div className= 'bottom'>
45                 <div className='feels'>
46                 {data.main ? <p className='bold'>{data.main.feels_like.toFixed()}°C</p> : null}
47                   <p>Feels like</p>
48                 </div>
49                 <div className='humidity'>
50                 {data.main ? <p className='bold'>{data.main.humidity}%</p> : null}
51                   <p>Humidty</p>
52                 </div>
53                 <div className='wind'>
54                 {data.wind ? <p className='bold'>{data.wind.speed.toFixed()} KM/H</p> : null}
55                 <p>Wind Speed</p>
56                 </div>
57               </div>
58           }
59          </div>
60         </div>
61       );
62     }
63     
64     export default App;
```

<br/>

**Displaying data in App.js**

\-`data.name`<swm-token data-swm-token=":src/App.js:34:5:7:`          &lt;p&gt;{data.name}&lt;/p&gt;`"/> Fetches name property from captured response in the data object.<br/>
\-`{data.main.temp.toFixed()}°`<swm-token data-swm-token=":src/App.js:37:11:22:`          {data.main ? &lt;h1&gt;{data.main.temp.toFixed()}°C&lt;/h1&gt; : null}`"/> Fetches temp property from captured response in the data object. The value is rounded and displayed as a whole number.<br/>
\-`{data.weather[0].main}`<swm-token data-swm-token=":src/App.js:40:11:20:`        {data.weather ? &lt;p&gt;{data.weather[0].main}&lt;/p&gt; : null}`"/> The if statement that checks if the main proper existed in the data object. If it exists it displays the value if it doesn’t it displays null.<br/>
\- `{data.name`<swm-token data-swm-token=":src/App.js:43:1:4:`      {data.name != undefined &amp;&amp; `"/> The expression checks if the name property is defined which is fetched from the input field. It removes the bottom container div from the page when it refreshes.<br/>
\- {data.main ? <p `className=&#39;bold&#39;&gt;{data.main.feels_like.toFixed()}°C&lt;/p&gt;`<swm-token data-swm-token=":src/App.js:46:11:32:`            {data.main ? &lt;p className=&#39;bold&#39;&gt;{data.main.feels_like.toFixed()}°C&lt;/p&gt; : null}`"/> : null} The jsx expression checks if the main feels like property exists, it then displays a whole number or integer values otherwise it displays null.<br/>
\- {data.main ? <p `className=&#39;bold&#39;&gt;{data.main.humidity}%&lt;/p&gt;`<swm-token data-swm-token=":src/App.js:50:11:26:`            {data.main ? &lt;p className=&#39;bold&#39;&gt;{data.main.humidity}%&lt;/p&gt; : null}`"/> : null} The jsx expression checks if the humidity property exists, it then displays the value otherwise it displays null.<br/>
\-{data.wind ? <p `className=&#39;bold&#39;&gt;{data.wind.speed.toFixed()}`<swm-token data-swm-token=":src/App.js:54:11:27:`            {data.wind ? &lt;p className=&#39;bold&#39;&gt;{data.wind.speed.toFixed()} KM/H&lt;/p&gt; : null}`"/> KM/H</p> : null} The jsx expression checks if the main wind speed property exists, it then displays a whole number or integer values otherwise it displays null.
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/App.js
```javascript
30          <div className='container'>
31           
32           <div className='top'>
33             <div className='location'>
34               <p>{data.name}</p>
35             </div>
36             <div className='temp'>
37               {data.main ? <h1>{data.main.temp.toFixed()}°C</h1> : null}
38             </div>
39             <div className='description' >
40             {data.weather ? <p>{data.weather[0].main}</p> : null}
41             </div>
42           </div>
43           {data.name != undefined && 
44                 <div className= 'bottom'>
45                 <div className='feels'>
46                 {data.main ? <p className='bold'>{data.main.feels_like.toFixed()}°C</p> : null}
47                   <p>Feels like</p>
48                 </div>
49                 <div className='humidity'>
50                 {data.main ? <p className='bold'>{data.main.humidity}%</p> : null}
51                   <p>Humidty</p>
52                 </div>
53                 <div className='wind'>
54                 {data.wind ? <p className='bold'>{data.wind.speed.toFixed()} KM/H</p> : null}
55                 <p>Wind Speed</p>
56                 </div>
57               </div>
58           }
59          </div>
60         </div>
61       );
62     }
```

<br/>

Imports google font
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
1      @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@100;200;300;400;500;600;700&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
2      
```

<br/>

\-Sets the default css property values.
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
3      * {
4        box-sizing: border-box;
5        margin: 0;
6        padding: 0;
7      }
```

<br/>

\-Default properties.
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
9      body {
10       font-family: 'Outfit', 'Segoe UI', 'Roboto', 'Oxygen',
11         'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
12         sans-serif;
13       -webkit-font-smoothing: antialiased;
14       -moz-osx-font-smoothing: grayscale;
15     }
16     
```

<br/>

\- Paragraph tag font size.
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
17     p {
18       font-size: 1.6rem;
19     }
20     
```

<br/>

\- H1 tag font size.
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
21     h1 {
22       font-size: 6rem;
23     }
```

<br/>

The root div that holds all the elements
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
25     .app {
26       width: 100%;
27       height: 100vh;
28       position: relative;
29       background-color: rgba(0,0,0,0.4);
30       color: #fff;
31     }
32     
```

<br/>

\- This adds a background image to the page and allows it to move according to the size of the screen.
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
33     .app:before {
34       content: '';
35       background: url('./assets/image.jpg') no-repeat center center/cover;
36       position: absolute;
37       width: 100%;
38       height: 100%;
39       top: 0;
40       left: 0;
41       z-index: -1;
42     }
```

<br/>

\-This targets the search input field and places it in the center of the page with a little of padding “1rem”.
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
44     .app .search {
45       text-align: center;
46       padding: 1rem;
47     }
```

<br/>

\-This targets the input field’s appearance.<br/>
\-padding: .7rem `1.5rem;`<swm-token data-swm-token=":src/index.css:50:7:10:`  padding: .7rem 1.5rem;`"/> Top and bottom padding of 7rem and left and right padding of 1.5rem.<br/>
\-`font-size:`<swm-token data-swm-token=":src/index.css:51:1:4:`  font-size: 1.2rem;`"/> 1.2rem; Font size of the value the input field holds.<br/>
\- `border-radius:`<swm-token data-swm-token=":src/index.css:52:1:4:`  border-radius: 25px;`"/> 25px; This curves the left and right border of the input field by 25%.<br/>
\-border: 1px solid `rgba(255,255,255,`<swm-token data-swm-token=":src/index.css:53:8:15:`  border: 1px solid rgba(255,255,255, 0.8);`"/> 0.8); and background: `rgba(255,255,255,`<swm-token data-swm-token=":src/index.css:54:4:11:`  background: rgba(255,255,255, 0.1);`"/> 0.1); This places a thin border of 1px and changes its color to the rgba value stated figures.<br/>
\- color: #f8f8f8; Font color of input field.

<!-- empty line --><br/>

<!-- empty line --><br/>
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
49     .app input {
50       padding: .7rem 1.5rem;
51       font-size: 1.2rem;
52       border-radius: 25px;
53       border: 1px solid rgba(255,255,255, 0.8);
54       background: rgba(255,255,255, 0.1);
55       color: #f8f8f8;
56     }
```

<br/>

\-This sudo class targets the color of the place holder of the input field.
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
57     
58     ::placeholder {
59       color: #f8f8f8;
60     }
```

<br/>

This adds the width span size of the page to the top container. It also adds a 1rem margin to the top and bottom of the container and adds auto width to right and left of the container (div).
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
74     .app .top {
75       width: 100%;
76       margin: 1rem auto;
77     }
```

<br/>

\-This targets the wrapper div of all the elements and makes the page mobile responsive.<br/>
\-`max-width:`<swm-token data-swm-token=":src/index.css:63:1:4:`  max-width: 700px;`"/> 700px; This places a maximum width value constraint on the container div and helps provide the mobile responsive feel to the elements and content on in the div.<br/>
\- height: 490px; height value of the container.<br/>
\- margin: auto; margin is the size between elements which is set to auto.<br/>
\- padding: 0 1rem; Padding of elements on the left and right.<br/>
\- position: relative; This allows to move the elements on the page.<br/>
\- top: 10%; Adds spacing from the top of the page.<br/>
\-`flex-direction:`<swm-token data-swm-token=":src/index.css:70:1:4:`  flex-direction: column;`"/> column; Adds responsiveness to the page and arranges the elements and content in 1 column when on a smaller screen (Device).<br/>
\- `justify-content:`<swm-token data-swm-token=":src/index.css:71:1:4:`  justify-content: space-between;`"/> space-between; This places horizontal spacing between the elements.<br/>
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
62     .container {
63       max-width: 700px;
64       height: 490px; 
65       margin: auto;
66       padding: 0 1rem;
67       position: relative;
68       top: 10%;
69       display: flex;
70       flex-direction: column;
71       justify-content: space-between;
72     }
```

<br/>

<br/>

<br/>

\-position: relative; The relative property allows to position the div at different positions on the page.<br/>
\- right: -90%; Moves the description div to the right of the page.<br/>
\- `transform-origin:`<swm-token data-swm-token=":src/index.css:82:1:4:`  transform-origin: 0 0;`"/> 0 0; The property value pair below allows to change position of the element.<br/>
\- transform: `rotate(269deg);`<swm-token data-swm-token=":src/index.css:83:4:8:`  transform: rotate(269deg);`"/> This rotates the element.
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
79     .app .description {
80       position: relative;
81       right: -90%;
82       transform-origin: 0 0;
83       transform: rotate(269deg);
84     }
```

<br/>

\-display: flex; The property value pair below allows the use the flex-direction property value pair.<br/>
\- justify-content: `space-evenly;`<swm-token data-swm-token=":src/index.css:88:6:9:`  justify-content: space-evenly;`"/> The property value below adds responsiveness to the page and places even spaces between the elements and content. Therefore when the screen size changes the content maintain uniform space between them. This provides a better responsive feel to the page.<br/>
\- `text-align:`<swm-token data-swm-token=":src/index.css:89:1:4:`  text-align: center;`"/> center; This aligns the text in the div in the center.<br/>
\- width: 100%; This gives a 100% width to the bottom container.<br/>
\-margin: 1rem auto; Padding of the element at the top and bottom of the page. The padding on the right and left is set to auto which aligns the container in the center.<br/>
\- padding: 1rem; Padding of 1rem at the top, right, bottom and left of the container.<br/>
\-`border-radius:`<swm-token data-swm-token=":src/index.css:93:1:4:`  border-radius: 12px;`"/> 12px; Rounds the four edges of the div by 12px.<br/>
\- background-color: `rgba(255,255,255,`<swm-token data-swm-token=":src/index.css:94:6:13:`  background-color: rgba(255,255,255, 0.2);`"/> 0.2); This adds a background color to the give which gives it its light silver appearance.<br/>
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
86     .app .bottom {
87       display: flex;
88       justify-content: space-evenly;
89       text-align: center;
90       width: 100%;
91       margin: 1rem auto;
92       padding: 1rem;
93       border-radius: 12px;
94       background-color: rgba(255,255,255, 0.2);
95     }
```

<br/>

<br/>

<br/>

\-Every element with a class name of “hold” will be bold or have a darker and bigger appearance.
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 src/index.css
```css
96     
97     .bold {
98       font-weight: 700;
99     }
```

<br/>

This file was generated by Swimm. [Click here to view it in the app](/repos/Z2l0aHViJTNBJTNBcmVhY3RXZWF0aGVyQXBwJTNBJTNBTWFhelBybw==/docs/i321r).
