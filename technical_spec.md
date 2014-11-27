#Quotation App

- - -

###Technical Spec

- - -

1. **hardware spec**  
    1.1. `device`  
    This app will work on android devices.  
    1.2. `minSdkVersion`  
    Oldest android phone can run on: API level 8, platform 2.2, FROYO.  
    1.3. `targetSdkVersion`  
    Newest android phone can run on: API level 19, platform 4.4, KitKat.

2. **database**  
    2.1. `parse.com`  
    It is free/pay online back-end tools services. Developer can relay on parse.com to take care of the back-end remotely while focus on front-end work. database is one of the services we are using to host our quotes and quote categories. Database, table, and data can be created on parse.com user interface, or by use API parse.com provided kind like using Object-relational mapping.  
    2.2. `database table`  
    We use online database instead of local phone storage is because we can continue add more quotes remotely, and all user will get it. We have 2 tables "Quotation" store all quotes, and "Category" store all categories. The app will query quotes from Quotation table and display on the screen. Parse.com database is online, so user **HAVE TO** be able to connect to internet to get the quotes.  
    2.3. `register parse.com account`  
    Developer need to register an account first. After that, you will get application key and 
client key. Then, download the ParseStarterProject and put in your application key and client key there, then you can run the starter project, build your project on top of it.  
    2.4. `parse.com API`  
    After you got a runnable ParseStarterProject. When you create table on parse.com you need to add it to ParseApplication.  
    2.5. `parse.com free usage limitation`  
    Limitation can be change all the time please check it once a while. Free account gets 30 request per second per one jab.  

3. **our general layout**  
    3.1. `screenOrientation`  
    We set to portrait mode only, so no rotation. We just want to save our self some trouble.

4. **guide pages**  
    4.1. `ViewPager`  
    ViewPager is a android class for screen swiping / sliding. We are using a already make ViewPager starter project. **?????? Saman please help edit this part ??????**    
    4.2. `Button`  
    Click the Button to go to splash screen.  

5. **splash screen**  
    5.1. `Handler`  
    To set wait time by use Handler class to create a thread to wait for amount of time. Usually splash screen is use to load up stuff for the app. The wait time can be longer, usually have a nice background logo image or text displaying.  

6. **home page**  
    6.1. `ListView with custom view for each item`  
    The home page will show quotes by android class ListVeiw, order by category. By customize the view instead of using the build in view for each list item, we can add image to each list item and format the displaying text. The build in view only allow text.  
    6.2. `EndlessScrollListener`  
    When user scroll down, more quote will show up until the last quote, this is done by EndlessScrollListener. It request more item if over the threshold of remaining item before the end of current page. It is more useful for loading huge amount of data or data size will keep on growing by the second; which only load a small amount at a time not all at once to your device, so the wait time will be cut into section, or not overflow your View class capacity. First download a already  make EndlessScrollListener.java, find one that come with documentation that tell you how to use it. Some useful parameter or variable for your app to use or pass in; EX: "page" load more base on fix number of item consider one page, "totalItemsCount" load more base on number of item reached, "visibleThreshold" start load more base on how many items left before reach the end of current page.  
    6.3. `navigation drawer`  
    User can bring out the overflow menu by press the ActionBar icon on the upper left, or the icon on the upper right, or slide a finger from left edge of screen by using ActionBarDrawerToggle, DrawerLayout, ListView, and android.support.v4.widget.DrawerLayout. Developer can just use a Menu instead of navigation drawer to do the same thing. **?????? Saman please help edit this part ??????**  
    6.4. `overflow menu`  
    This menu contain category of quotes. By select one of them, home page will only show quotes from selected category. **?????? Saman please help edit this part ??????**  
    6.5. `Menu`  
    When clicking on the search icon on the upper right it will go to search page. We just the Menu as a Button, since it Menu sit on the ActionBar, we can free up a Button space about 50*20dp of the screen.  

7. **search page**  
    7.1. `EditText`  
    The search box can take any String as search key, it does "and" search only, it use the user input String to match each quotes that we query from the online database parse.com, user input need to match exactly it is a EditText class.  
    7.2. `Menu`  
    Press the menu icon on the upper right to go to home page. Again it is function like a Button.  
