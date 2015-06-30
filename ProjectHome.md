RXTX is a native lib providing serial and parallel communication for the Java Development Toolkit (JDK). It provides the gnu.io package, which is an open-source version of the Java Comm API. The RXTX main page is: http://users.frii.com/jarvi/rxtx/

This is a complete and self contained OSGI bundle that provides the entire RXTX serial and parallel communications capability withing an OSGI framework.

We principally use it to communicate with USB-attached devices from within Java applications.

This package builds on RXTX code base 2.0-7pre1. It incorporates many significant edits and improvements including:

> Embedding and auto-loading of native libraries within the JAR file. Currently supports:
> > LINUX i386
> > LINUX ARM

> Improved serial port identification
> Many bug fixes and exception catches

The OSGI bundle is tested and debugged for Apache Felix > 2.0. There are no Felix-specific features, so it should run without issues on Equinox, Knoplerfish, etc.

Use:
This SINGLETON bundle is configured for LAZY loading and exports the 'gnu.io' package to the OSGI environment.

Operation:
Native libraries are stored in the 'resources' directory. When called, the appropriate native library is extracted and copied to the directory specified in the system property 'java.io.tmpdir'. On Linux, this is typically /tmp. To see how this works, look at the org.rfsdb.util.EmbeddedLibraryLoader class.