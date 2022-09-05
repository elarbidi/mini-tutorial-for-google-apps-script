# Google apps script

---

---

## Build custom user interfaces in Google Sheet using Apps Script

# Builder custom menu in Google Sheets

### why bother to make a custom menu

1. you can make it easy for users to run Google Apps script Functions that are associated with your spreadsheet (even non-technical users can use those functions)
2. • You can link to functions that require the user's authorization from a menu item and users will be asked to approve the necessary permissions when they select that menu item.

---

### Hands-on 🤓

in this part, we will try *to build an admin menu and add it to the menu ba*r


```jsx
var createCuMenu = ()=> {
  var MenuName = "admin pannel";//the menu name
  var Menu = SpreadsheetApp.getUi().createMenu(MenuName);// init the menu obj
  Menu.addItem("here the menu  item name" , "namedFunction");//add item to the menu the forst prm is the name of that item and the other is for the name of the function
  Menu.addToUi();//add the the menu to the UI
}
```

in the code above I add a menu name admin pannel using  :

```jsx
const menu = SpreedSheetApp.getUi().CreateMenu(/*menu name*/);
```

add an item to the menu : 

```jsx
menu.addItem(/*name of the item*/, /*name of the fucntion*/);
```

add everything to the spreadsheet page : 

```jsx
me.addToUi()
```

and like that, we were able to add a menu to our sheet 


---

### let's make it more complex 🥸

now let's add more items to the admin menu 

- **REMEMBER**
    
    ```jsx
    /**** to create menu ****/
    SpreedSheetApp.getUi().CreatMenu(/* menu name */);
    ```
    
    ```jsx
    //to add menu to the item wee need to use the function addItem()
    Menu.addItem(/*name*/, /*function*/);
    ```
    
    ```jsx
    // we can add everything to the spreadsheet by the function 
    	.addToUI();
    ```
    

hands-on 🤓

1 - let make a function to make menu creation easy and creep the code clean 

```jsx
function menuInit(name){
	return (SpreedSheetApp.getUi()
					.createMenu(name))
}
```

2 let add items to our menu :

```jsx
function createCustomMenu(){
	var menu = menuInit("adminPannel");
	menu.addItem("item A","itemA");
	menu.addItem("item B","itemB");
	menu.addToUi()
}
```

3- let's's add a separator : 

separator in google apps is  the sane as <br> in HTML!

to use separator : 

```jsx
menu.addSeparator()
```

with Little magic 

```jsx
function createCustomMenu(){
	var menu = menuInit("adminPannel");
	menu.addItem("item A","itemA");
	menu.addSeparator()
	menu.addItem("item B","itemB");
	menu.addToUi()
}
```

4 - add a sub-menu inside the menu :

to add a sub-menu all we need to do is to create another menu and add it by using the function ( addSubMenu(sub-menu) )

```jsx
function createCustomMenu(){
	var menu = menuInit("adminPannel");
	menu.addItem("item A","itemA");
	menu.addSeparator()
	menu.addItem("item B","itemB");
	var subMenu = menuInit("subMenu");
	subMenu.addItem("item D","item D");
	menu.addSubMenu(subMenu);
	menu.addToUi()
}
```
