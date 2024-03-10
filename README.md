# rosdoc_lite

A [forked repository](https://github.com/solarcleano/rosdoc_lite) of the [rosdoc_lite official repository](https://github.com/ros-infrastructure/rosdoc_lite). It contains a fix to the hyperlink in the footnote of the webpage, so that it points to Solarcleano's GitHub.

[rosdoc_lite](http://wiki.ros.org/rosdoc_lite) is a [ROS](http://www.ros.org) package that wraps documentation tools like [doxygen](http://www.doxygen.org), [sphinx](http://sphinx-doc.org),
and [epydoc](http://epydoc.sourceforge.net/), for convenient generation of ROS package documentation.

It also generates online documentation for the ROS wiki.

This package provides only the `rosdoc_lite` command.  It has no supported Python or C++ API.
 
## How to install

- Use git clone on this repository in your robot catkin workspace.  
- Make sure you have installed the following packages (they should already be installed if you are using the melodic docker image) :  
    - ros-melodic-full-desktop
- Compile with catkin. 
  
  Eg. *`catkin build rosdoc_lite`*   
  
## How to use  

This package allows to generate the documentation related to a specific package as long as the comments of the source code follows the docstring format for Python and the Doxygen format for C++. Examples of such formats are available in the package package_template.

### Generate documentation

- To use rosdoc_lite as it was originally designed, use the rosdoc_lite command followed with the name of the package you want to generate the documentation for, as well as the destination directory. This should generate the documentation in the target folder within a "html" folder. Then, you just need to open any of the .html file inside in your browser. It should be noted that the front page of the documentation is accessible with the "index.html" file.

Eg. *`rosdoc_lite $SOME_PACKAGE -o $SOME_FOLDER_OUTPUT -q`*  

- You can also retrieve the sections of the package_template's CMakeLists.txt relative to documentation generation and put them in your own package's CMakeLists.txt.  
If you add the ENABLE_DOC_GENERATION argument, as well as the "## Documentation ##" section, you can generate the documentation by passing -DENABLE_DOC_GENERATION=ON when building your package with catkin.

Eg. *`catkin build $SOME_PACKAGE -DENABLE_DOC_GENERATION=ON`*    

## How to configure  

rosdoc_lite makes use of the Doxygen software to generate the documentation. The Sphinx and Epidoc softwares are also available but they are not yet used in our packages.

### Doxygen

#### With the rosdoc.yaml file

The configuration of Doxygen is usually done through a Doxyfile, a file generated after the first use of the software. However, we don't have access to it with rosdoc_lite. Rather, the parameters are set in the rosdoc.yaml file of the doc folder. You just need to put the name of the parameter you want to set with the same syntax as you would do with a Doxyfile, except all characters should be changed to lowercase.

The list of parameters is available [here](https://www.doxygen.nl/manual/config.html).

## How to test
/

## Troubleshooting
/