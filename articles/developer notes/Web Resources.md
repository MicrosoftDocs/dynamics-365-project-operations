Project Operations Web resources, whether marked customizable or not, do not support customizations. Web resources include the ones listed in [Web resource types
](https://learn.microsoft.com/en-us/dynamics365/customerengagement/on-premises/developer/web-resources?view=op-9-1#web-resource-types).

# Unsupported customizations – Examples
1.	Taking a dependency on the code or components added in the Project Operations web resource.
    For example, taking dependency on the methods, constants or variables defined in a Project Operations Javascript web resource is not supported.
2.	Updating the Project Operations web resources is not supported. This can cause unpredictable side effects when Project Operations ships an update for the web resource.
   
If you have any of the above customizations, please remove the customizations and instead create your own web resources.
