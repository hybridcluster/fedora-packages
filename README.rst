**This is a deprecated repository.**
**New packages are in the Flocker repository and are, at the time of writing, uploaded to Amazon S3.**

Packages for ClusterHQ's flocker that aren't available in fedora.


clusterhq-release package
~~~~~~~~~~~~~~~~~~~~~~~~~

This is a meta-package that contains the yum repository definitions for archive.clusterhq.com.

To build and upload the package, run the following commands on a fedora 20 machine::

   rpmbuild --define="_sourcedir ${PWD}" --define="_rpmdir ${PWD}/results" -ba clusterhq-release.spec
   gsutil cp -a public-read results/noarch/$(rpm --query --specfile clusterhq-release.spec --queryformat '%{name}-%{version}-%{release}').noarch.rpm gs://archive.clusterhq.com/fedora/clusterhq-release.fc20.noarch.rpm
