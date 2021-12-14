# Virtual Machine with multiple data disks

## Description

The template may be used for creating a virtual machine with multiple data disks. VM can have zero or several data disks. Each disk have their options (size, SKU etc.) and when you attach them you may also specify caching.
In this template as part of the virtual machine deployment three types of dada disks are created:
- data disks
- log disks
- additional disks

Each type is represented with the parameters specifying number of disks, SKU, size and caching.

The virtual machine created by the template is supposed to be placed into an availability set that also may be created by template, that depends on the parameter createAvailabilitySet.

## Outcome

The virtual machine from the example shown below has been created with the size Standard_DS3_v2 and 5xP40, 3xP30 and 1xP3 data disks with Read only caching enabled for 5xP40.

<img src="pictures/disks.PNG" width="800">

## Additional information

The template has been created based on information shared in the following two posts and repositories.

- https://dev.to/omiossec/azure-how-to-build-a-reusable-multi-data-disks-vm-arm-template-2ghn

- https://github.com/OmegaMadLab/OptimizedSqlVm
