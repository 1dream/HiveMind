## HiveMind

HiveMind is a project management application featuring project/task,
request, and content (wiki) management. There is support for multiple
vendors, multiple clients, flexible billing rates, time recording,
expenses, invoicing, payments, and general ledger.

### Running HiveMind

To run HiveMind you need Moqui Framework and Mantle Business Artifacts as
well as HiveMind itself. Moqui supports a few methods for setup and
deployment as described in the documentation here:

http://www.moqui.org/framework/docs/RunDeploy.html

The easiest way to try HiveMind is with the binary distribution available
on GitHub:

https://github.com/moqui/HiveMind/releases

If you don't have gradle or ant installed you can use this command line to
run Java directly:

$ java -Xmx256M -XX:MaxPermSize=128m -jar moqui-${version}.war

### Build and Run Locally

To get the latest Moqui, Mantle, and HiveMind and run locally you'll need
JDK 7 or later, Gradle 1.6 or later (1.12 recommended but anything in the 1 series, NOT the Gradle 2 series),
and either a git client or you can use the
"ZIP" download links on each project page on github. The github project
pages are at:

https://github.com/moqui/moqui
https://github.com/moqui/mantle
https://github.com/moqui/HiveMind

Java can be downloaded here (make sure to use the Download button under
the "JDK" column, not the under the "JRE" column):

http://www.oracle.com/technetwork/java/javase/downloads/index.html

Gradle can be downloaded here (use a release before 2.0 in the Previous Releases section):

http://www.gradle.org/downloads

To download Moqui/Mantle/HiveMind source and build/run locally use the
following steps:

#### Step 1: Download Moqui Framework

Zip: https://github.com/moqui/moqui/archive/master.zip
Git: git://github.com/moqui/moqui.git

From either source you should have a "moqui" directory for the next steps.
If you use the Zip download change the directory name from "moqui-master"
to "moqui".

#### Step 2: Download Mantle Business Artifacts

Zip: https://github.com/moqui/mantle/archive/master.zip
Git: git://github.com/moqui/mantle.git

Put the "mantle" directory in the "moqui/runtime" directory so it is
located at "moqui/runtime/mantle". If you use the Zip download change the
name of the directory from "mantle-master" to "mantle" to make sure the
directory under the "moqui/runtime" directory has the correct name.

#### Step 3: Download HiveMind PM

Zip: https://github.com/moqui/HiveMind/archive/master.zip
Git: git://github.com/moqui/HiveMind.git

Put the "HiveMind" directory in the "moqui/runtime/component" directory so
it is located at "moqui/runtime/component/HiveMind". If you use the Zip
download change the name of the directory from "HiveMind-master" to
"HiveMind" to make sure the directory under the "moqui/runtime/component"
directory has the correct name.

#### Step 4: Build and load seed and demo data

From the "moqui" directory run "gradle load".

This will build Moqui and load data from Moqui, Mantle and HiveMind into
an embedded Derby database.

#### Step 5: Run Moqui

From the "moqui" directory run "gradle run".

#### Step 6: Access the HiveMind application

In your browser go to:

http://localhost:8080/apps/hm

Use the button in the lower-left corner of the screen login as John Doe.

### Setup Commands Quick Reference

Java 7 is recommended: http://www.oracle.com/technetwork/java/javase/downloads/index.html

Gradle 1.12 recommended (use a release before 2.0 in the Previous Releases section): http://www.gradle.org/downloads

Here are command line steps, and you can do the same thing with a Git desktop app:

    $ git clone git@github.com:moqui/moqui.git moqui
    $ cd moqui/runtime/
    $ git clone git@github.com:moqui/mantle.git mantle
    $ cd component/
    $ git clone git@github.com:moqui/HiveMind.git HiveMind
    $ cd ../.. (to the moqui directory)
    $ gradle load
    $ gradle run

Here are steps for a basic update:

    $ cd moqui
    $ git pull
    $ cd runtime/mantle
    $ git pull
    $ cd ../component/HiveMind
    $ git pull
    $ cd ../../.. (to the moqui directory)
    $ gradle cleanAll
    $ gradle load
    $ gradle run
