# FunNews
This is a Personalized News App with Android.

## App Demo 
<img src="https://github.com/oliver1112/FunNews/blob/main/assets/newsdemo.gif" alt="structure" width="300"/>

- In Home fragment, click the like button or swipe the card right to save news. And click the dislike or swipe the card left to view the next one.
- View the saved news detail at Save fragment. Click the delete button to remove it from local storage.
- Use Search fragment to search the keyword of news you like. 

## MVVM
The main players in the MVVM pattern are:

- The View — that informs the ViewModel about the user’s actions
- The ViewModel — exposes streams of data relevant to the View
- The DataModel — abstracts the data source. The ViewModel works with the DataModel to get and save the data.

The architecture of this project is as follows:

<img src="https://github.com/oliver1112/FunNews/blob/main/assets/MVVM.png" alt="structure" width="450"/>

## Retrofit
This project creates the network layer with Retrofit and its underlying OkHttp. The Retrofit are RESTful API setup on Android.
I use Gson to deserialize the model. Retrofit instantiates the interface into the actual implementation.

The source of the news is from https://newsapi.org/. The RESTful APIs provide many different query parameters, this project mainly use two endpoints:
- https://newsapi.org/v2/everything
- https://newsapi.org/v2/top-headlines


## RecyclerView
A RecyclerView is used for displaying a large amount of data in the fashion of a list (single column) or a grid (multi-column). 
The common RecyclerView case:

- A large collection of dynamic content, might be infinite.
- Each item in the collection is similar in structure.
- Limited memory space to hold all the data and their views.

A recycler view requires an Adapter and LayoutManager. An Adapter is for creating each item view and binding the data to a view by recycling. 
A LayoutManager is for controlling how the views are organized, typically in a list or in a grid.

Here are the steps to implement a RecyclerView:
- Create the layout for item views.
- Create an adapter that contains the ViewHolder.
- Link the item_view layout to the ViewHolder and finish create/bind ViewHolder process in the recyclerView
- Pass the Adapter to the RecyclerView and setup the LayoutManager.


## Jetpack Navigation
Jetpack Navigation Component: [Official Getting Started](developer.android.com/guide/navigation/navigation-getting-started) and
[Documentation](https://developer.android.com/jetpack/androidx/releases/navigation). Single activity paradigm with multiple 
fragments. Page navigation and app flow is controlled in one place, a navigation graph. The benefits are:
- Declarative visual screen flow and navigation all in one.
- Type safety with fragment safe args, it’s now been abstracted away.
- Great support for deeplinks with back stack handling.

The navigation graph of fragments are as follows:

<img src="https://github.com/oliver1112/FunNews/blob/main/assets/Navigation.png" alt="ERD" width="700"/>

## Room Database
Room is built on top of SQLite. It was introduced in 2018. Room has the following concepts:
- Database contains the database holder and serves as the main access point for the underlying connection to your app’s persisted, relational data.
- Entity represents a table within the database.
- DAO contains the methods used for accessing the database.

The advantage of Room:
- Sometimes apps doesn’t have network, like in tunnel or on plane.
- App need to support offline mode.
- App consume both network and local generated structure data.

## Ideas for Future Work
- Add a social share button to share the news through SMS, email, WeChat, and Facebook.
- Use Kotlin to write this App to better handle multi-thread cases.
