# Schema Repository Contents

This repository contains all of the published record definitions, validation schemas, and eventually other things like view definitions and more.  A clone of this repository should reside on the http://schemas.delving.eu so that it can be updated at will.

There is an index of all of the contents in the form of **schema-repository.xml** which has entries for all the versions available in the prefix-named subdirectories where the files are actually contained.

Each entry in the index contains a hash string which the client verifies to be the hash of the contents of the schema file.  As a rule, nobody should ever change one of these hash values, and commits to this repository should be done using pull requests so that other developers can verify that no changes have been made.  The only thing that should be allowed to happen is that somebody creates a new version (number) of a schema and adds an accompanying entry in the index XML file.

The schema-repo sub-project of the sip-creator is responsible for ensuring that the clients verify the hashes, and it is therefore also the way that a developer can find out what a new hash value should be.  Running **TestSchemaRepository** there after adding a new version should reveal what the hash value should be if it is absent or incorrect.  Once the test runs successfully (and no hashes have been changed, only a new entry added), it can be pushed into a new branch for issuing a pull request.  Later it can be pulled on the website.

The unit test also tests the website, so it should be possible to verify that they are identical once the process has been completed.

For local development this repository is sought in directories nearby the current directory, and the hashes are not verified so that developers can freely make changes locally until they decide to work out the hash and do the publishing as described above.
