.. include:: /icons.txt

#########################
Installation Instructions
#########################


*************
Prerequisites
*************

The Ryzen AI Software supports AMD processors with a Neural Processing Unit (NPU). Refer to the release notes for the full list of :ref:`supported configurations <supported-configurations>`.

The following dependencies must be installed on the system before installing the Ryzen AI Software:

.. list-table::
   :widths: 25 25
   :header-rows: 1

   * - Dependencies
     - Version Requirement
   * - Windows 11
     - build >= 22621.3527
   * - Visual Studio
     - 2022
   * - cmake
     - version >= 3.26
   * - Python (for creating standalone virtual environments)
     - Latest version

|

|warning| **IMPORTANT**:

- Visual Studio 2022 Community: ensure that `Desktop Development with C++` is installed

- Python: ensure the required Python version is installed and available through the Windows ``py`` launcher when creating standalone virtual environments. The Ryzen AI MSI also provides its own virtual environment.

|

.. _install-driver:

*******************
Install NPU Drivers
*******************

- Download the NPU driver installation package (update with latest link) :download:`NPU Driver <https://account.amd.com/en/forms/downloads/ryzenai-eula-public-xef.html?filename=NPU_RAI1.5_280_WHQL.zip>`

- Install the NPU drivers by following these steps:

  - Extract the downloaded ZIP file.
  - Open a terminal in administrator mode and execute the ``.\npu_sw_installer.exe`` file.

- Ensure that NPU MCDM driver (Version:specif the version, Date:updated date) is correctly installed by opening Task Manager -> Performance -> NPU0.


.. _install-bundled:

*************************
Install Ryzen AI Software
*************************

- Download the RyzenAI Software installer (insert RAI-1.9 MSI installer link) :download:`ryzen-ai-1.9.0.msi <https://account.amd.com/en/forms/downloads/ryzen-ai-software-platform-xef.html?filename=ryzen-ai-1.5.0.msi>`.

- Launch the MSI installer and follow the instructions on the installation wizard:

  - Accept the terms of the Licence agreement
  - Provide the destination folder for Ryzen AI installation (default: ``C:\Program Files\RyzenAI\``)
  - Specify the name for the virtual environment (default: ``C\Program Files\RyzenAI\1.9.0\venv``)

  .. image:: images/venv-pic-1.png
   :align: center


The Ryzen AI Software packages are now installed in the virtual environment created by the installer.

.. image:: images/env-create-after-installation-2.png
   :align: center


.. note::

     The latest updates with LLM performance improvements are available in the RAI 1.5.1 release. Download it from the link :download:`ryzen-ai-1.5.1.msi <https://account.amd.com/en/forms/downloads/ryzen-ai-software-platform-xef.html?filename=ryzen-ai-1.5.1.msi>`.


.. _quicktest:


*********************
Test the Installation
*********************

The Ryzen AI Software installation folder contains test to verify that the software is correctly installed. This installation test can be found in the ``quicktest`` subfolder.

- Open a Command Prompt or (search for "Miniforge Prompt" in the Windows start menu)

- Activate the virtual environment created by the Ryzen AI installer:

.. code-block::

   "C:\Program Files\RyzenAI\1.9.0\venv\Scripts\activate.bat"

- Run the test:

.. code-block::

   cd %RYZEN_AI_INSTALLATION_PATH%/quicktest
   python quicktest.py


- The quicktest.py script sets up the environment and runs a simple CNN model. On a successful run, you will see an output similar to the one shown below. This indicates that the model is running on the NPU and that the installation of the Ryzen AI Software was successful:

.. code-block::

    [Vitis AI EP] No. of Operators :   NPU   398 VITIS_EP_CPU     2
    [Vitis AI EP] No. of Subgraphs :   NPU     1 Actually running on NPU     1
    Test Passed



.. note::

    The full path to the Ryzen AI Software installation folder is stored in the ``RYZEN_AI_INSTALLATION_PATH`` environment variable.





..
  ------------

  #####################################
  License
  #####################################

 Ryzen AI is licensed under `MIT License <https://github.com/amd/ryzen-ai-documentation/blob/main/License>`_ . Refer to the `LICENSE File <https://github.com/amd/ryzen-ai-documentation/blob/main/License>`_ for the full license text and copyright notice.
