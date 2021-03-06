---
title: Custom DataProvider
page_title: Custom DataProvider
description: Custom DataProvider
slug: virtualgrid-custom-dataprovider
tags: dataprovider
published: True
position: 3
---

# Custom DataProvider

The __DataProvider__ mechanism of __RadVirtualGrid__ various mechanisms for extending its default behavior. This can be achieved by inheriting the __DataProvider__ object and overriding its methods or properties.

#### __[C#] Example 1: Defining a Custom DataProvider__

	public class CustomDataProvider: DataProvider
    {
        public CustomDataProvider(IEnumerable source)
            :base(source)
        {
 
        }
    }

#### __[C#] Example 2: Applying the Custom DataProvider__

	this.VirtualGrid.DataProvider =
                new CustomDataProvider(this.myCollection);

By inheriting the default __DataProvider__, the following methods and properties are exposed for customization.

### Properties

* __InitialRowCount__: If not overriden, gets the value that is set to the __InitialRowCount__ property of __RadVirtualGrid__

* __InitialColumnCount__: If not overriden, gets the value that is set to the __InitialRowCount__ property of __RadVirtualGrid__

* __ShouldPushEditValueToGrid__: When an editor is provided for the [Editing]({%slug virtualgrid-editing%}) operation, its edited value needs to be manually pushed to underlying source and to the grid through its __PushCellValue__ method. If the __ShouldPushEditValueToGrid__ property is overriden and returns a __True__ value, updating the control with the edited property value will be done automatically.

### Methods

* __OnCellEditEnded__: The method that is called when the __CellEditEnded__ event is raised

* __OnCellValueNeeded__: The method that is called when the __CellValueNeeded__ event is raised

* __OnEditorNeeded__: The method that is called when the __EditorNeeded__ event is raised

* __OnEditorValueChanged__: The method that is called when the __EditorValueChanged__ event is raised

* __OnHeaderValueNeeded__: The method that is called when the __HeaderValueNeeded__ event is raised

## See Also

* [Editing]({%slug virtualgrid-editing%})

* [Insert and Remove Data]({%slug virtualgrid-insert-data-and-remove-data%})

* [Pinned Rows and Columns]({%slug virtualgrid-pinned-rows-and-columns%})