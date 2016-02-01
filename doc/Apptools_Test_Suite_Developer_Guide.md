# Apptools Test Suite Developer Guide

## 1. Overview

This document is intended for developers who contribute Apptools test cases development.

You are supposed to have gained the following knowledge:

- Where to download Apptools test source codes and how to run them
- How to download and run Testkit-lite

    Note: Testkit-lite is a test execution framework. For details, see [https://github.com/testkit/testkit-lite](https://github.com/testkit/testkit-lite).

## 2. Test Suite Source Layout

The layout of test source codes should:

- Meet the requirements of Testkit-lite
- Meet project requirements, for example, support tests can be executed on corresponding platforms

The test suite source layout is detailed as follows:

### 1. apptools-android-tests Source Layout
apptools-android-tests/

├── apptools/

├── icon/

├── report/

├── testapp/

├── tools/

├── arch.txt

├── COPYING

├── host.txt

├── icon.png

├── inst.apk.py

├── mode.txt

├── README.md

├── suite.json

├── tests.full.xml

├── tests.xml

├── version.txt

- Documents:
  - README: an introduction of the test suite, and precondition for AppTools on test host.

- Test-related files and folders:
  - apptools/: a serial of source files or directories for test cases that are well organized by components or features to be tested, e.g. apptools/xxx
  - icon/: icons are used for test cases
  - report/: ./allpairs.py is create report directory for package name
  - testapp/: sampleapps are used for test cases
  - tools/: set up environment for run tests
  - arch.txt: the type of test device
  - host.txt: the type of test host
  - mode.txt: the type of build mode
  - version.txt: the Crosswalk which to test

- Build/pack support:
  - suite.json: configure file for the test suite

The following files and folders are mandatory in :

- suite.json
- tests.xml
- tests.full.xml

### 2. apptools-ios-tests Source Layout
apptools-ios-tests/

├── apptools/

├── report/

├── testapp/

├── tools/

├── README.md

├── suite.json

├── tests.full.xml

├── tests.xml

### 3. apptools-linux-tests Source Layout
apptools-linux-tests/

├── apptools/

├── icon/

├── report/

├── testapp/

├── tools/

├── COPYING

├── icon.png

├── inst.deb.py

├── README.md

├── suite.json

├── tests.full.xml

├── tests.xml

### 4. apptools-windows-tests Source Layout
apptools-windows-tests/

├── apptools/

├── icon/

├── report/

├── testapp/

├── tools/

├── COPYING

├── icon.ico

├── manifest.json

├── README.md

├── suite.json

├── tests.full.xml

├── tests.xml

## 3. Test Case File Naming Convention

**Template**

shortDescriptionForTestPurpose.py

shortDescriptionForTestPurpose.html

- The file name for auto cases must be end with .py. The first letter of each word is lowercase, and connect with "_"
- The file name for manual cases must be end with .html. The first letter of each word is uppercase, and connect with "_"

**Examples**

manifest_apk_name.py

Manifest_Command_Line_EnableWebGL.html

## 4. Test Case File Template

class TestCrosswalkApptoolsFunctions(unittest.TestCase):

    def subcase1(self):

    def subcase2(self):

    def subcase3(self):

if __name__ == '__main__':
    unittest.main()

- TestCase file must be written like this, "def" represents one subcase
- Similar test points can be put in one testCase file
- One testCase file may includes one or multiple subcases

## 5. Subcase Naming Convention

**Template**

test\_shortDescriptionForTestPurpose

- The first letter of each word is lowercase, and connect with "_"

**Examples**

test_activity_name_normal

test_update_app_version

## 6. Test Case Classification (<testcase\> field in tests.xml)
Refer to the `Web_Test_Suite_Developer_Guide.md`.

## 7. How to Add New Test Suite to Apptools
To add a new suite to Apptools, perform the following steps:

1) Fork and clone the crosswalk-test-suite project from

  [https://github.com/crosswalk-project/crosswalk-test-suite](https://github.com/crosswalk-project/crosswalk-test-suite)

  **Note** : you must sign up for the GitHub first.

2) Copy a test suite to the spec under testing, for example, "apptools-platform-tests".

3) Replace platforms in manifest.json:

    "xwalk_target_platforms": ["platforms"]

4) Update suite.json to change the type of built app:

    "pkg-list": {
    "apk": {//the type of built app

5) Update README to introduce the test suite, and precondition for AppTools on test host.

6) Add new cases to the test suite. For details, see chapter 3 "Test Case File Template"

## 8. How to Contribute New Cases to Test Suite Package

To contribute new cases to test suite package, perform the following steps:

1) Design new test case according to Apptools Features and add new case information to **tests.xml**.

2) Develop test cases by following the "Test Case File Template" and put it under apptools/ floder.

## Appendix 1 `tests.full.xml` and `tests.xml`

See [tests.xml definition and sample](./Tests_XML_Definition_and_Sample.md).
