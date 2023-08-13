# Experimental OpenJDK Build for arm32

As there is no official arm32 CI build for OpenJDK I tried to set-up this
GitHub Actions workflow to emulate a RaspiOS using qemu.

## Status 2023/08/13

* ✅ Checkout OpenJDK source tree
* ✅ Run RaspiOS emulator with `qemu`
* ✅ Install build dependencies
* ✅ Install bootstrap JDK
* ✅ Run `configure`
* ❌ Run `make images`


Unfortunately I did not succeed so far due to [this qemu limitation](https://gitlab.com/qemu-project/qemu/-/issues/263).
As a result the OpenJDK build fails with this exception:

    java.io.UncheckedIOException: java.nio.file.FileSystemException: .: Value too large for defined data type
        at java.base/java.nio.file.Files$2.hasNext(Files.java:3778)
        at java.base/java.util.Iterator.forEachRemaining(Iterator.java:132)
        at java.base/java.util.Spliterators$IteratorSpliterator.forEachRemaining(Spliterators.java:1921)
        at java.base/java.util.stream.AbstractPipeline.copyInto(AbstractPipeline.java:509)
        at java.base/java.util.stream.AbstractPipeline.wrapAndCopyInto(AbstractPipeline.java:499)
        at java.base/java.util.stream.AbstractPipeline.evaluate(AbstractPipeline.java:575)
        at java.base/java.util.stream.AbstractPipeline.evaluateToArrayNode(AbstractPipeline.java:260)
        at java.base/java.util.stream.ReferencePipeline.toArray(ReferencePipeline.java:616)
        at java.base/java.util.stream.ReferencePipeline.toArray(ReferencePipeline.java:622)
        at java.base/java.util.stream.ReferencePipeline.toList(ReferencePipeline.java:627)
        at jdk.compiler/com.sun.tools.javac.file.JavacFileManager$DirectoryContainer.list(JavacFileManager.java:491)
        at jdk.compiler/com.sun.tools.javac.file.JavacFileManager.list(JavacFileManager.java:778)
        at jdk.compiler/com.sun.tools.javac.code.ClassFinder.list(ClassFinder.java:748)
        ... (rest of output omitted)