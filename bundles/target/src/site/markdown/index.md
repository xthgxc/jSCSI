# Introduction

iSCSI defines a server-client protocol for block-based data transmission whereas the client is denoted as initiator while the server is called target. This bundle represents the server denoted target for the rest of the documentation.

## Acting as fully functional target

The target is designed to act as a standalone Java-process in a JVM offering the ability to support multiple targets. The configuration can take place either over Java directly or over defined XML-files validated against given schemas. After initialization including the creation of any storage-modules, the target is able to receive any PDU representing any read-/write- or meta-operation occurring on the target fully compliant to the http://www.ietf.org/rfc/rfc3720.txt iSCSI RFC 3720.

## Robust and Flexible

The jSCSI-target represents a plain-java based adapter for providing an iSCSI-target directly out of your Java environment. By leveraging from the concurrency-features of Java 5+, the target offers variable ways to handle any incoming data request. Furthermore, the mapping if the iSCSI RFC to object-oriented paradigms within jSCSI offers the ability to map iSCSI to different storage backends as denoted below:
![storage](/images/storage.graffle)
As clearly visible, jSCSI offers the ability to map any backend implementing the interface org.jscsi.target.storage.IStorageModule to the iSCSI RFC. At the moment, the interface is implemented only by an asynchronous file backend as well as a synchronized file environment. Each request is handled multi-threaded where possible. It is important to note, that the multi-threaded ability of jSCSI is only utilized after login when accessing any target for read-/write-purposes.

## Own needs, own requirements

jSCSI was created at the http://www.uni-konstanz.de University of Konstanz at the http://www.informatik.uni-konstanz.de/arbeitsgruppen/disy Distributed Systems Group out of the necessity to provide an architecture for storing blocks directly out of Java without any hassle of filesystems.

Below, see a small history of the jSCSI-target:

* Transferred from sourceforge to github in 2011.
* Transferred to github in 2011.
* The target was developed as a bachelors' project of Andreas Ergenzinger in 2011.
The jSCSI-target is hosted with jSCSI https://github.com/disy/jSCSI under the BSD License and guarded by Travis-CI. It can be found under the bundle jscsi-target.