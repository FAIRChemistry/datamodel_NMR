<h2 align="center">
  Markdown Example for sdRDM
</h2>

<p align="center"> 
This is an example of how to set up a data model using the Software-Driven Research Data Management (sdRDM) library which is based on abstract object models. Furthermore, the sdRDM library supports the conversion of data models defined in the Markdown format.</p>
 

Data models defined in the Markdown format follow these conventions:

- **Modules** are denoted by a heading level 1 ```#```
- **Objects** are started with a heading level 3 ```###``` 
- Each object contains **fields** in bold as a list &rarr; ```- __name__```
- **Required fields** are denoted with an asterix &rarr; ```- __name*__```
- Each field has **options** as a list of name to value mapping &rarr; ```- Type: string```

**Field options**

Each field in an object can hold options relevant for mapping to another data model (e.g. a standardized format) and general information such as its type and description. In the following is a collection of all native and required fields:

- **Type** - Required option to denote the data type. Please note, this can also contain other objects defined in this document.
- **Multiple** - Whether or not this field can contain multiple values. Setting to ```True```will result in a ```List[dtype]``` annoatation in the software.
- **Description** - Required option to describe the field. This should be a brief description that explains what the attribute is about.

**Inheritance**

In order to inherit attributes to another object, the object definition additionally includes the name of the parent object in italic wrapped with brackets:

&rarr; ```## Child [_Parent_]```

In the following an example data model is defined using above rules. Feel free to use this example also as a template for your own application.

---------
# Data model for NMR

This data model aims to comprehensively describe NMR experiments. Currently, 1D NMR time-course experiments are covered by it.

### Root

This is the root of the data model and contains all objects related to NMR experiments.

- __id*__
  - Type: string
  - Description: Unique identifier for the dataset
- __title*__
  - Type: string
  - Description: Title of the work
- __description*__
  - Type: string
  - Description: Describes the content of the dataset.
