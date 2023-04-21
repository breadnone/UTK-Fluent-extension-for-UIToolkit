# UTK-Fluent-extension-for-UIToolkit
A simple fluent extension for UIToolkit in Unity3D.  
UTK is just a simple c# extension to make working with c# in UIToolkit bearable. You can still use UIToolkit documentation to work with this extension.  

Requirement:  
Unity 2022.2 and above.  

![sampleUtk](https://user-images.githubusercontent.com/64100867/233624446-f833f050-3d79-415f-bc21-4f896ea5d7fd.png)


  
Example syntaxes:  
```
//Set width & height property of VisualElement  
visualElement.Size(100, 100); //Pizel based size
visualElement.Size(100, 100, true, true) //Percent based size

//Or via width / height property
visualElement.Width(100, true).Height(100, true); //Uses boolean overload set to true for Percent/dynamic style

//Chaining  
visualElement.FlexRow().FlexGrow(1).BcgColor(Color.yellow);

//Will always return self can safely be cached when/wherever
var vis = visualElement.Margin(5, true).Padding(12); // sets margin on all sides with dynamic size.  

//Parenting. set parent flex in the end (AddChild will return the parent)
myParent.AddChild(vis1).AddChild(vis2).AddChild(vis3);

//Returns the parent
var visParent = myParent.AddChild(vis2); 

myChild.AddParent(myParent); //Sets parent from directly from child

//Hex color support
visualElement.BcgColor("#0063B1"); //Invalid hex code, will fallback to Color.clear.

//Rounded Corners + border
visualElement.RoundCorner(12, true).Border(12, Color.white);

//Events
//All events starts with `On`.. e.g: OnMouseEnter, OnFocusOut, OnPointerEnter
myTextField.OnValueChanged(x=>{Debug.Log(x.newValue);}); //Equal to RegisterValueChanged<T>.

//Equal to registerCallback<MouseDownEvent>();
visualElement.OnMouseDown(x=> {Debug.Log("Click!");}); 

//All registered events will be unregistered via DetachPanel (Or when removed from hierarchy)
```

  
  
Custom controls made with this extension(available in templates folder)  
![hXfRpQuBMN](https://user-images.githubusercontent.com/64100867/233269564-a9b7ba88-c794-41e0-bc5d-f98331a6f4fa.gif)![HawSiIB9Tn](https://user-images.githubusercontent.com/64100867/233269630-db91c657-e5c6-4087-b42f-1de6a355a618.gif)![SYbDUn5twn](https://user-images.githubusercontent.com/64100867/233269709-187d783b-79be-4ddf-b7bf-d81015daa5bd.gif)![Odq7DtujgR](https://user-images.githubusercontent.com/64100867/233269740-17eaa432-ce08-4d29-a289-dc51ba3e8141.gif)
![FAvrHSn47N](https://user-images.githubusercontent.com/64100867/233269764-2fea21c3-1a48-4ce0-b094-59b7947c3586.gif)![Zk110dQuMb](https://user-images.githubusercontent.com/64100867/233269824-171a5eaf-a84b-4349-b324-2e79dd9ac799.gif)![BBPAuj1OzU](https://user-images.githubusercontent.com/64100867/233269852-66e3b30d-67f8-4509-8441-63804f422b24.gif)![mWMNg3EnKN](https://user-images.githubusercontent.com/64100867/233270240-8a5b4bf7-724d-4756-85c2-37acfd704620.gif)



