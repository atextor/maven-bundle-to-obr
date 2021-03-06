maven-bundle-to-obr
===================

Given groupId, artifactId and version of a Maven package, downloads the package and all dependencies and uses [BND](http://www.aqute.biz/Bnd/Bnd) to convert
each package into a valid [OBR](http://felix.apache.org/site/apache-felix-osgi-bundle-repository.html) (OSGi bundle repository) bundle.

Additionally, it takes all jars found in the 'additional' directory and BNDifies them.

The use case is to automatically prepare the needed packages, ready to be dragged&dropped into the local repository in [Bndtools](http://bndtools.org/), while
the Maven repository support in Bndtools is still in the making.


*Requirements*

* Ant

*Usage example*

	ant -Dorg=org.apache.jena -Dname=apache-jena -Dversion=2.7.1

	# will only process jars in the 'additional' directory
	ant

will produce a directory "wrapped" that contains an OBR jar (.bar) for each dependency of apache-jena. Jars that are already OSGi bundles are detected and copied as-is into the "wrapped" directory.

