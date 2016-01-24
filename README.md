Jetty 9.3.x with HTTP/2
---------------

As Java8 can't negotiate ALPN with stock classes, a few JRE classes need to be replaced.
As outlined in the [Jetty ALPN documentation](http://www.eclipse.org/jetty/documentation/current/alpn-chapter.html) the used `alpn-boot-*.jar` has to match your JRE.

```
java -Xbootclasspath/p:<path_to_alpn_boot_jar> ...
```

Therefore if the exception below is raised on start, copy the matching `alpn-boot-*.jar` to a common location and amend your launch configuration.

```
java.lang.IllegalStateException: org.eclipse.jetty.alpn.ALPN must be on JVM boot classpath
```