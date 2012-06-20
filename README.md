maven-bundle-to-obr
===================

Given groupId, artifactId and version of a Maven package, downloads the package and all dependencies and uses [BND](http://www.aqute.biz/Bnd/Bnd) to convert
each package into a valid [OBR](http://felix.apache.org/site/apache-felix-osgi-bundle-repository.html) (OSGi bundle repository) bundle.

The use case is to automatically prepare the needed packages, ready to be dragged&dropped into the local repository in [Bndtools](http://bndtools.org/), while
the Maven repository support in Bndtools is still in the making.

*Requirements*

* Ant

*Usage example*

	ant -Dorg=org.apache.jena -Dname=apache-jena -Dversion=2.7.1

will produce a directory "wrapped" that contains an OBR jar (.bar) for each dependency of apache-jena. It will also create a "lib" directory that
contains the downloaded jars, which you can inspect or delete.

