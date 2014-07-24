:title: clojure
:description: How to configure shippable.yml file for clojure 
:keywords: yml,clojure,lein,lein2

.. _langclojure:


Clojure
========

This section helps you to create a shippable.yml file for your clojure project.

- Tell us what your build environment is. This is an optional setting and if omitted Ubuntu 12.04 is used as a default.
    .. code-block:: python
        
        # Build Environment
        build_environment: ubuntu1204


-  Set the appropriate language and the version number. Clojure minions use ``lein`` by default to set the runtime platform.
	.. code-block:: python
	
     		# language setting
              language: clojure
        	# lein tag
	      lein: lein2

- Use **install** key to install the required dependencies for your project.  
	.. code-block:: python

            install: lein protobuf install

 
- **Test scripts**:  Use **script** key in shippable.yml file to specify what command to run tests with. The default command to run leiningen test suite is **lein test** 
       .. code-block:: python

            script: lein test

**Build Examples**

Want to see build examples? Reference our :ref:`Clojure build samples <clojure>` .
 

