# Could not launch the product because the associated workspace is currently in use by another Eclipse

If you are seeing following error at the beginning of the Eclipse or any RCP based product then here is the solution:  
  
**Error Message:**  
  
****`Could not launch the product because the associated workspace is currently in use by another Eclipse application.`  
  
or  
  
`Workspace in use or cannot be created chose a different one.`  
  
  
**Solution :**  
go to workspace location  
remove file **&lt;workspace location&gt;/.metadata/.lock**  
  
**Reason:**  
  
****Through eclipse, user can create multiple Workspace locations. One Workspace location can be edited by one user at a time. A workspace contains the data related to various project configuration and local file storage.  
  
To avoid multiple users to access the same workspace, eclipse is maintaining a **".lock"** file inside the Workspace. Eclipse will remove this **".lock"** file when you will close the Eclipse.  
  
But in some cases, the Eclipse will crash due to some error, due to which it could not able to remove ".lock" file from the Workspace. As a result of this, when you open the Eclipse with the same workspace location, it will show an error: "Could not launch the product because the associated workspace is currently in use by another Eclipse application." or "Workspace in use or cannot be created chose a different one."  
  
In this case, if we remove the **".lock"** file from **&lt;workspace location&gt;/.metadata/.lock**, then it will resolve the issue.

