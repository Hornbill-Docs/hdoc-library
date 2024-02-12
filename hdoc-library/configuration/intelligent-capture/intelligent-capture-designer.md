Intelligent Capture is a graphical workflow tool that provides a new and simple way to define the capturing of information for a particular application. An application that uses Intelligent Capture will include serveral small forms for collecting information related to the application. These forms can be optionally added, ordered, and branched depending on the information being captured.

## Nodes
When building a capture workflow there are a few different nodes that are available to use when considering your design.

* **Start**<br>Every capture workflow will have a Start node. This is the entry point for all capture scripts.
* **Form**<br>You can choose from a number of pre-configured small forms (in Form Properties) and place them in the sequence you need.
* **Custom Form**<br>Allows you to create your own form complete with custom fields and values.
* **Branch**<br>Allows a custom expression to alter the flow to show different PCF's.
* **Switch**<br>Allows you to link capture workflows together and seamlessly switch from one to another
* **End**<brEvery capture flow will have at least one of these to end the flow.
* **Cancel**<br>The Cancel node allows the capture workflow to exit without any further processing. This behaves the same as if the user had selected the cancel button that is available when filling out a capture. The user will be returned to where the Intelligent Capture was initiated from.

## Branches
In Intelligent Capture, branches allow the workflow designer to send the user down different routes to potentially collect different information based on the choices that are made on previous capture forms.

A branch node will always inherit the outcomes from its parent capture forms. This means that if you place a branch node after the request details form (as shown in the screenshot), the only pieces of data that you can branch on are the Summary and Description fields (only 2 fields on this default form).
When branching to a new capture it is important to ensure that all Custom Forms have unique names to prevent mapped fields from being overwritten.

### Custom Expressions
To add a custom expression to a branch node you must first connect the decision node to the next node in the flow.
* You can then click the linking line and define your custom expression.
* You can define multiple outcomes from a branch node, however, you must always have at least one valid outcome, otherwise, the capture workflow could potentially have nowhere to go which will result in an error.
A branch node can have a maximum of three outcomes. If you require more than three outcomes you can link one branch node to another branch node using a No Match link and you can then add an outcome option to the second or subsequent branch node.
* You can use variable values from any form that has been used in the capture workflow before the branch question for example from the Customer Search form you may use the Customer Type variable to branch on
* You can branch on a global variable such as where the capture is being used. For example, if it is being used by an analyst in the user app you may want to branch to different forms compared to if the same capture was being used by a customer on either the customer or service portals.


## Switch Capture
The Switch Capture node provides the ability to seamlessly move to or link capture workflows together. One example of where this may be useful is in Service Manager when choosing a Request Catalog item from the Services capture form, the switch process can be used to switch to the capture flow which is assigned to the chosen request catalog item.

Using this node replaces the previous behavior of jumping from an initial capture workflow to another, and in essence, any forms used in both are evaluated and re-used when jumping, it also removes the need to evaluate which forms in the second capture workflow to use, and any issues associated with capture forms being skipped.

Using this node, will in effect continue from the initial capture workflow, into the next capture workflow rather than replace it. This means it does not need to evaluate which forms to skip, it simply ignores any forms already used in the initial capture.

Advantages of using the Switch Capture Node
* When switching processes the UI for the analyst is smooth as you are linking one process to another not replacing one with another.
* The ability to return to the forms in the initial process capture flow, once you have switched or linked to a second process capture flow in order to change choices or even change which pcapture to switch too.
* You don't need to include the same forms in both captures, for example, the Customer Search form could just be used in the initial capture, and removed from the catalog item capture (if it already exists it will be ignored).

#### Example
Following the use of the Services Details form, you may include a Branch node and have two outcomes.

1. Using a Custom Expression, perform a check to see if 'Service details -> catalogProgressiveCaptureId Is Set (if a request catalog item has been selected) from here link to the Switch Capture node
2. Using another Custom Expression perform the same check but set this to Is Not Set (a Service rather than a request catalog item has been selected) and build your logic accordingly, equally you could define multiple other outcomes from this branch node to reflect the different service choices and paths you wish to take.

On the Switch Capture node, you can configure this to link to a specific new process or use a Variable to link to the capture linked to the request catalog item that has been chosen. In this example, this is what we will do and the Variable to use would be Service details -> catalogProgressiveCaptureId

:::tip
With the introduction of the Switch Capture option, the behavior will alter slightly on the Services Details form, is as much as the user will now have to select the Next button if they are selecting either the Service or the Request Catalog Item in order to progress the capture workflow. Previously if a Request Catalog Item was chosen the capture would immediately progress without the need to click Next.
:::

## Sharing and Visibility
Intelligent capture owners will be able to view their own captures, and captures which have been shared with them from the capture workflow list.

When creating or editing a capture it is possible via the Manage Process Settings and Grant Access To option to share your process with:

* Roles
* Users
* Groups

It is possible to share captures with multiple users, roles and groups. Once a capture has been shared, the user will be able to view the capture from the Intelligent Capture list.

To remove visibility to a specific User, Role or Group simply select the Trash Can icon next to the item you wish to stop sharing the capture with.

To enforce the above sharing and visibility controls, ensure the system setting security.bpm_access_controls.enabled is set to On from the Platform Configuration.

## Intelligent Capture Options
Each capture workflow has a number of configuration options

* **Download**<br>Download the definition file - downloads to a .txt file, a copy of the current capture workflow.
* **Upload**<br>Upload a pcf.txt file to the capture workflow - this will replace the current capture workflow content.
* **Print**<br>Print out a document that provides a graphical representation of the capture workflow.
* **Save** (Validate, Activate, De-activate)<br>After the creation or editing of a capture workflow, your workflow needs to be saved and then activated to make it available for use. Any capture workflow that you wish to keep but do not have available for use can be deactivated.