# iSeeE3 User Help

## Creating your first project

When opening the editor for the first time, there will be a default project title "Project 1" that you can access straight away. You can rename the project or simply create a new one by clicking on the "New Explanation Experience" button. Then click on the "Editor" button to start building your own explanation experiences.
<p align="center">
<img width="815" alt="image" src="https://user-images.githubusercontent.com/71895708/207810403-43b26356-25b4-44de-b6c4-518f3201e58e.png">
</p>

## First Look at the Interface

iSeeE3 is a tool based on behavior trees that allows you to build and customize your own explanation experiences. For an empty expanation experience, the interface will look like this:
<p align="center">
<img width="1916" alt="image" src="https://user-images.githubusercontent.com/71895708/207819838-2a3e9c65-d439-4577-8efe-dcdbf722a44d.png">
</p>

At first glance, the interface might be overwhelming, so we cover each of its components next:

### Main Panel

The main panel is where we can visualize our tree and interact with it by clicking on its componentes and dragging and dropping new nodes. For a newly created project, the main panel will only contain the root node of the default tree that is created. We will see how to interact with the panel in the next sections.

### Menu Bar
<p align="center">
<img width="842" alt="image" src="https://user-images.githubusercontent.com/71895708/207816324-3c59dbba-a747-41bd-8155-89b2d2a2398e.png">
</p>

The menu bar allows you to quickly save the project and access the tool settings, undo and redo changes, and the following submenus:

- **Project:** to save the project, import and export a project, tree or node as JSON, access the editor settings, and create new explanation experiences and custom nodes.
- **Edit:** provides access to basic edition functionalities, such as undo and redo actions, copy, cut, paste and remove selected nodes.  
- **View:** For zooming in and zooming out, as well as organizing the nodes of a tree for a cleaner presentation.
- **Selection**: to select or deselect a node, select a subtree or invert the current selection.
- **Random Generator:** to randomly generate explanation experiences by specifying certain parameters, such as the minimum number of nodes and the depth of the trees to be created.
- **Help:** provides access to this help guide and a video tutorial.


### Trees and Nodes Panel
<p align="center">
<img width="349" alt="image" src="https://user-images.githubusercontent.com/71895708/207820894-e5be21fe-e740-4013-8523-d3efd338c1db.png">
</p>

On the left side of the interface, we have the trees and nodes panel. The **"Trees"** section displays all the trees contained in the current project, highlighting the currently selected tree in blue. We can create new trees by hovering over the panel title and clicking on the "New" button. To remove any of the trees, simply hover over its name and click on "Remove".

The **"Nodes"** section contains all the nodes that can be appended to the current tree. You can use different types of nodes:

- **Explanation Method:** A generic explanation method node. The explanation method that will be used is specified from the *Properties* panel, as well as the execution parameters that may be needed.
<p align="center">
<img width="290" alt="image" src="https://user-images.githubusercontent.com/71895708/207826990-f26ea539-9e01-49de-8aa7-33d77c3bfa07.png">
</p>

- **Failer and Succeeder:** return failure or success accordingly.
<p align="center">
<img width="545" alt="image" src="https://user-images.githubusercontent.com/71895708/207826544-323b8977-f1ca-4613-8180-e4a81e30c6ba.png">
</p>

- **Condition:** 
<p align="center">
<img width="268" alt="image" src="https://user-images.githubusercontent.com/71895708/207827039-0bf5c5fb-cd6b-448c-85d9-3b2287cc2184.png">
</p>

- **Sequence and Priority:** These are considered composite nodes. They act as connectors an indicate the execution flow of many nodes. A sequence node will return immediately upon one of its children failing. A priority node will return inmediately upon on of its children succeeding.
<p align="center">
<img width="217" alt="image" src="https://user-images.githubusercontent.com/71895708/207827132-b3950731-ce3f-493e-8c1f-53ece28ea42f.png">
</p>

- **Decorator Nodes:** these are additional nodes aim to define the execution flow in ahigher level. It is possible to use the "Repeat" nodes to represente loops in our behavior trees. The "Inverter" node simply inverts the returned value of another node (failure/success)

<p align="center">
<img width="953" alt="image" src="https://user-images.githubusercontent.com/71895708/207829559-b802d64f-400d-4df6-8610-af19f95af080.png">
</p>




### Properties Panel

The *Properties* panel allows to define and modify the individual properties of a node. The view of this panel may change depending on the node that is selected. The root node is a special case, as is represents the whole tree, and its properties will persist on the entire tree object. 

The *Properties* panel of the **root node** looks like this:

<p align="center">
<img width="293" alt="image" src="https://user-images.githubusercontent.com/71895708/207836434-11a66c43-a497-4765-8b77-014a0f62dfb3.png">
</p>


- **Run BT button:**  executes the entire behavior tree.
- **Intent:** it allows to rename the current explanation experience.
- **Description and Properties:** a description for this tree can be added in the provided text field. Additional properties can be added as key value pairs vy clicking on the "+" button.
- **Model:** a dropdown menu with the names of the models that were uploaded to the iSee database. You can select the model you want explain, or see how to *include your own*. To execute a behavior tree, a model must be selected.
- **Query:** If you wish to include local explanation methods, a query (data instance) must be given. This query can be provided as plain text selecting the tabular data type, or as a file, which exclusive for image. Please keep in mind the input format expected by the model when providing and image file as a query. If the model you selected requires preprocessing of the image (i.e requires a different encoding from RGB for the input), then provide the query as plain text containg the matrix with the pixel values.
- **Save:** Saves the specified query (if any). If a new query is provided afterwards, then it will overwrite the previous one.

Most nodes have properties like title, description and user-defined properties:

<p align="center">
<img width="289" alt="image" src="https://user-images.githubusercontent.com/71895708/207841650-5e4b068c-cbd8-4f42-88cd-5cdb6bbc7ea7.png">
</p>

However, explanation method nodes are initially generic, waiting for a specific method to be selected. Hovering over the title of this node will display a drop-down menu that allows you the select the explanation method that you want. After selecting the desired method, the *Properties* panel will be updated, changing the name of the node and including the execution parameters (Params section) that are unique to that explanation method:

<p align="center">
<img width="292" alt="image" src="https://user-images.githubusercontent.com/71895708/207842600-c108605d-bb77-4fba-b436-0121cece8347.png">
</p>

Hovering over the names of the parameters, you can get information about what is the expected input format and their effect on the generated explanation. If parameters are left blank, default values will be given so execution is not affected. However, there are methods that may exceptionally require a parameter to be specified by the user, so it is encouraged to check the documentation for each specific parameter.

Finally, the *Properties* panel for explanation method nodes include a "Run" button, that will execute this explanation method, given that you have specified a model and query if required, and that the node is attached to the behavior tree.

## Building and Executing Explanation Experiences:

The process for building and executing explanation experiences can be summarized in the following steps:

1. **Open an existing project or create your own.**
2. **Select and existing explanation experience from the *Trees* section or create a new one.**
3. **Select the root node and define its properties.** 
4. **Select the model that will be used for explanations and provide a query if needed. Remember to save the query.**
  
  <p align="center">
  <img width="557" alt="image" src="https://user-images.githubusercontent.com/71895708/207846884-0d6da57e-890f-47cc-81a3-a13402093058.png">
  </p>
  
5. **Drag and drop the desired nodes from the *Nodes* section to build your explanation experience. In this example, we build a simple tree that ensures that at least one global an one local explanation is provided to the user:**

<p align="center">
<img width="1110" alt="image" src="https://user-images.githubusercontent.com/71895708/207848462-66f4c4d8-fc5f-4760-b75f-19d98e2af927.png">
</p>

6. **Specify execution parameters for the explanation methods (if necessary).**
7. **Execute the behavior tree or each individual method.**





 
 

