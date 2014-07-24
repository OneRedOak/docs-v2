:title: Python samples
:description: A brief description about Python-sample
:keywords: Python, Language,version number, Install, Notification alerts

.. _python :

python-samples
==============

These samples will help you get started with Shippable. Test and Coverage tools used here are
`nose <https://pypi.python.org/pypi/nose>`_ and `coverage 3.7  <https://pypi.python.org/pypi/coverage/>`_ .

`Python Sample <https://github.com/Shippable/sample_python>`_

`Python Sample with MySQL <https://github.com/Shippable/sample_python_mysql>`_

`Python Sample with Postgresql <https://github.com/Shippable/sample_python_postgres>`_

`Python Sample with MongoDB <https://github.com/Shippable/sample_python_mongodb>`_

`Python Sample with CouchDB <https://github.com/Shippable/sample-python-couchdb>`_

`Python Sample with RethinkDB <https://github.com/Shippable/sample-python-rethinkdb>`_

`Python Sample with Neo4j <https://github.com/Shippable/sample_python_neo4j>`_

`Python Sample with Coveralls <https://github.com/Shippable/sample_python_coveralls>`_

`Python Sample with Elasticsearch <https://github.com/Shippable/sample_python_elasticsearch>`_

`Python Sample with Memcache <https://github.com/Shippable/sample_python_memcache>`_

`Python Sample with RabbitMQ <https://github.com/Shippable/sample_python_rabbitmq>`_

`Python Sample with Redis <https://github.com/Shippable/sample_python_redis>`_

`Python Sample with SQLlite <https://github.com/Shippable/sample_python_sqllite>`_

Keep the output generated for test and code coverage in the special folder Shippable/testresults and Shippable/codecoverage to get parsed reports parsed and to get a visualization of the reports.The test results must be generated in Junit format.

We need the yml file to analyze the project details. Add the shippable.yml file to the root of your repo by specifying:


**language :** Specify the language used to create the project. Python is used in this sample project.

**version number :** Specify the version numbers against which your build needs to run. The sample project uses "2.7".

**install :** Install the required dependencies for your repo here.

**script :** Specify the command to run the test and coverage and save the results to their respective 
shippable folders. If you have not created the folders, then you can create it using the before_script key.

**Notification alerts:**  Email notifications are added to get the alerts about the build status.

Here is the complete yml file for sample_python project.

.. code-block:: bash
    
   language: python

   python:
      - 2.7

   install:
      - pip install -r requirements.txt

   # Make folders for the reports
  
   before_script:
      - mkdir -p shippable/testresults
      - mkdir -p shippable/codecoverage

   script:
      - nosetests test.py --with-xunit --xunit-file=shippable/testresults/nosetests.xml
      - which python && coverage run --branch test.py
      - which python && coverage xml -o shippable/codecoverage/coverage.xml test.py

Enable the repo sample_python and run it using an Ubuntu minion. Once the build finishes execution, you can check for the console output, test and codecoverage results on the respective build's page.

