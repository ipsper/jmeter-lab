# liten setup en run lab för jmeter

1 [jmeter ](https://jmeter.apache.org/)
2 [jmeter_install ](https://jmeter.apache.org/)
3 [jmeter demo ](https://medium.com/@fatihmcicek/performance-testing-jmeter-00-92d497f5172f)
4 [jmeter best practices ](https://jmeter.apache.org/usermanual/best-practices.html)
5 [jmeter macos-release-notes ](https://developer.apple.com/documentation/macos-release-notes/appkit-release-notes-for-macos-14)
6 [jmeter for-performance-and-load-testing ](https://www.geeksforgeeks.org/how-to-use-jmeter-for-performance-and-load-testing/)

# Install

# prerequisite

```
java --version
[ $(java --version | grep -c OpenJDK) -eq 2 ] && echo "Installed"

```

## macOS java

```
brew install openjdk
```

### installation info

==> openjdk
For the system Java wrappers to find this JDK, symlink it with
sudo ln -sfn /opt/homebrew/opt/openjdk/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk.jdk

openjdk is keg-only, which means it was not symlinked into /opt/homebrew,
because macOS provides similar software and installing this software in
parallel can cause all kinds of trouble.

If you need to have openjdk first in your PATH, run:
echo 'export PATH="/opt/homebrew/opt/openjdk/bin:$PATH"' >> ~/.zshrc

For compilers to find openjdk you may need to set:
export CPPFLAGS="-I/opt/homebrew/opt/openjdk/include"

## linux java

```

```

## macOS jmeter

[jmeter install mac ](https://tejaksha-k.medium.com/a-step-by-step-guide-how-to-install-apache-jmeter-on-macos-6a9eb8bf3463)

```
brew install jmeter
```

## verify installation of jmeter

```
jmeter -v
```

WARNING: package sun.awt.X11 not in java.desktop
WARN StatusConsoleListener The use of package scanning to locate plugins is deprecated and will be removed in a future release
WARN StatusConsoleListener The use of package scanning to locate plugins is deprecated and will be removed in a future release
WARN StatusConsoleListener The use of package scanning to locate plugins is deprecated and will be removed in a future release
WARN StatusConsoleListener The use of package scanning to locate plugins is deprecated and will be removed in a future release
ERROR StatusConsoleListener FileManager (jmeter.log) java.io.FileNotFoundException: jmeter.log (Read-only file system)
java.io.FileNotFoundException: jmeter.log (Read-only file system)
at java.base/java.io.FileOutputStream.open0(Native Method)
at java.base/java.io.FileOutputStream.open(FileOutputStream.java:289)
at java.base/java.io.FileOutputStream.<init>(FileOutputStream.java:230)
at org.apache.logging.log4j.core.appender.FileManager$FileManagerFactory.createManager(FileManager.java:508)
	at org.apache.logging.log4j.core.appender.FileManager$FileManagerFactory.createManager(FileManager.java:488)
at org.apache.logging.log4j.core.appender.AbstractManager.getManager(AbstractManager.java:146)
at org.apache.logging.log4j.core.appender.OutputStreamManager.getManager(OutputStreamManager.java:112)
at org.apache.logging.log4j.core.appender.FileManager.getFileManager(FileManager.java:225)
at org.apache.logging.log4j.core.appender.FileAppender$Builder.build(FileAppender.java:102)
	at org.apache.logging.log4j.core.appender.FileAppender$Builder.build(FileAppender.java:55)
at org.apache.logging.log4j.core.config.plugins.util.PluginBuilder.build(PluginBuilder.java:124)
at org.apache.logging.log4j.core.config.AbstractConfiguration.createPluginObject(AbstractConfiguration.java:1162)
at org.apache.logging.log4j.core.config.AbstractConfiguration.createConfiguration(AbstractConfiguration.java:1083)
at org.apache.logging.log4j.core.config.AbstractConfiguration.createConfiguration(AbstractConfiguration.java:1075)
at org.apache.logging.log4j.core.config.AbstractConfiguration.doConfigure(AbstractConfiguration.java:679)
at org.apache.logging.log4j.core.config.AbstractConfiguration.initialize(AbstractConfiguration.java:264)
at org.apache.logging.log4j.core.config.AbstractConfiguration.start(AbstractConfiguration.java:313)
at org.apache.logging.log4j.core.LoggerContext.setConfiguration(LoggerContext.java:631)
at org.apache.logging.log4j.core.LoggerContext.reconfigure(LoggerContext.java:713)
at org.apache.logging.log4j.core.LoggerContext.reconfigure(LoggerContext.java:735)
at org.apache.logging.log4j.core.LoggerContext.start(LoggerContext.java:260)
at org.apache.logging.log4j.core.impl.Log4jContextFactory.getContext(Log4jContextFactory.java:154)
at org.apache.logging.log4j.core.impl.Log4jContextFactory.getContext(Log4jContextFactory.java:46)
at org.apache.logging.log4j.LogManager.getContext(LogManager.java:197)
at org.apache.logging.log4j.spi.AbstractLoggerAdapter.getContext(AbstractLoggerAdapter.java:136)
at org.apache.logging.slf4j.Log4jLoggerFactory.getContext(Log4jLoggerFactory.java:58)
at org.apache.logging.log4j.spi.AbstractLoggerAdapter.getLogger(AbstractLoggerAdapter.java:46)
at org.apache.logging.slf4j.Log4jLoggerFactory.getLogger(Log4jLoggerFactory.java:32)
at org.slf4j.LoggerFactory.getLogger(LoggerFactory.java:363)
at org.slf4j.LoggerFactory.getLogger(LoggerFactory.java:388)
at org.apache.jmeter.JMeter.<clinit>(JMeter.java:113)
at java.base/jdk.internal.misc.Unsafe.ensureClassInitialized0(Native Method)
at java.base/jdk.internal.misc.Unsafe.ensureClassInitialized(Unsafe.java:1160)
at java.base/jdk.internal.reflect.MethodHandleAccessorFactory.ensureClassInitialized(MethodHandleAccessorFactory.java:300)
at java.base/jdk.internal.reflect.MethodHandleAccessorFactory.newConstructorAccessor(MethodHandleAccessorFactory.java:103)
at java.base/jdk.internal.reflect.ReflectionFactory.newConstructorAccessor(ReflectionFactory.java:200)
at java.base/java.lang.reflect.Constructor.acquireConstructorAccessor(Constructor.java:549)
at java.base/java.lang.reflect.Constructor.newInstanceWithCaller(Constructor.java:499)
at java.base/java.lang.reflect.Constructor.newInstance(Constructor.java:486)
at org.apache.jmeter.NewDriver.main(NewDriver.java:257)
ERROR StatusConsoleListener Could not create plugin of type class org.apache.logging.log4j.core.appender.FileAppender for element File: java.lang.IllegalStateException: ManagerFactory [org.apache.logging.log4j.core.appender.FileManager$FileManagerFactory@4a83a74a] unable to create manager for [jmeter.log] with data [org.apache.logging.log4j.core.appender.FileManager$FactoryData@1349883]
java.lang.IllegalStateException: ManagerFactory [org.apache.logging.log4j.core.appender.FileManager$FileManagerFactory@4a83a74a] unable to create manager for [jmeter.log] with data [org.apache.logging.log4j.core.appender.FileManager$FactoryData@1349883]
at org.apache.logging.log4j.core.appender.AbstractManager.getManager(AbstractManager.java:148)
at org.apache.logging.log4j.core.appender.OutputStreamManager.getManager(OutputStreamManager.java:112)
at org.apache.logging.log4j.core.appender.FileManager.getFileManager(FileManager.java:225)
at org.apache.logging.log4j.core.appender.FileAppender$Builder.build(FileAppender.java:102)
	at org.apache.logging.log4j.core.appender.FileAppender$Builder.build(FileAppender.java:55)
at org.apache.logging.log4j.core.config.plugins.util.PluginBuilder.build(PluginBuilder.java:124)
at org.apache.logging.log4j.core.config.AbstractConfiguration.createPluginObject(AbstractConfiguration.java:1162)
at org.apache.logging.log4j.core.config.AbstractConfiguration.createConfiguration(AbstractConfiguration.java:1083)
at org.apache.logging.log4j.core.config.AbstractConfiguration.createConfiguration(AbstractConfiguration.java:1075)
at org.apache.logging.log4j.core.config.AbstractConfiguration.doConfigure(AbstractConfiguration.java:679)
at org.apache.logging.log4j.core.config.AbstractConfiguration.initialize(AbstractConfiguration.java:264)
at org.apache.logging.log4j.core.config.AbstractConfiguration.start(AbstractConfiguration.java:313)
at org.apache.logging.log4j.core.LoggerContext.setConfiguration(LoggerContext.java:631)
at org.apache.logging.log4j.core.LoggerContext.reconfigure(LoggerContext.java:713)
at org.apache.logging.log4j.core.LoggerContext.reconfigure(LoggerContext.java:735)
at org.apache.logging.log4j.core.LoggerContext.start(LoggerContext.java:260)
at org.apache.logging.log4j.core.impl.Log4jContextFactory.getContext(Log4jContextFactory.java:154)
at org.apache.logging.log4j.core.impl.Log4jContextFactory.getContext(Log4jContextFactory.java:46)
at org.apache.logging.log4j.LogManager.getContext(LogManager.java:197)
at org.apache.logging.log4j.spi.AbstractLoggerAdapter.getContext(AbstractLoggerAdapter.java:136)
at org.apache.logging.slf4j.Log4jLoggerFactory.getContext(Log4jLoggerFactory.java:58)
at org.apache.logging.log4j.spi.AbstractLoggerAdapter.getLogger(AbstractLoggerAdapter.java:46)
at org.apache.logging.slf4j.Log4jLoggerFactory.getLogger(Log4jLoggerFactory.java:32)
at org.slf4j.LoggerFactory.getLogger(LoggerFactory.java:363)
at org.slf4j.LoggerFactory.getLogger(LoggerFactory.java:388)
at org.apache.jmeter.JMeter.<clinit>(JMeter.java:113)
at java.base/jdk.internal.misc.Unsafe.ensureClassInitialized0(Native Method)
at java.base/jdk.internal.misc.Unsafe.ensureClassInitialized(Unsafe.java:1160)
at java.base/jdk.internal.reflect.MethodHandleAccessorFactory.ensureClassInitialized(MethodHandleAccessorFactory.java:300)
at java.base/jdk.internal.reflect.MethodHandleAccessorFactory.newConstructorAccessor(MethodHandleAccessorFactory.java:103)
at java.base/jdk.internal.reflect.ReflectionFactory.newConstructorAccessor(ReflectionFactory.java:200)
at java.base/java.lang.reflect.Constructor.acquireConstructorAccessor(Constructor.java:549)
at java.base/java.lang.reflect.Constructor.newInstanceWithCaller(Constructor.java:499)
at java.base/java.lang.reflect.Constructor.newInstance(Constructor.java:486)
at org.apache.jmeter.NewDriver.main(NewDriver.java:257)
ERROR StatusConsoleListener Unable to invoke factory method in class org.apache.logging.log4j.core.appender.FileAppender for element File: java.lang.IllegalStateException: No factory method found for class org.apache.logging.log4j.core.appender.FileAppender
java.lang.IllegalStateException: No factory method found for class org.apache.logging.log4j.core.appender.FileAppender
at org.apache.logging.log4j.core.config.plugins.util.PluginBuilder.findFactoryMethod(PluginBuilder.java:268)
at org.apache.logging.log4j.core.config.plugins.util.PluginBuilder.build(PluginBuilder.java:140)
at org.apache.logging.log4j.core.config.AbstractConfiguration.createPluginObject(AbstractConfiguration.java:1162)
at org.apache.logging.log4j.core.config.AbstractConfiguration.createConfiguration(AbstractConfiguration.java:1083)
at org.apache.logging.log4j.core.config.AbstractConfiguration.createConfiguration(AbstractConfiguration.java:1075)
at org.apache.logging.log4j.core.config.AbstractConfiguration.doConfigure(AbstractConfiguration.java:679)
at org.apache.logging.log4j.core.config.AbstractConfiguration.initialize(AbstractConfiguration.java:264)
at org.apache.logging.log4j.core.config.AbstractConfiguration.start(AbstractConfiguration.java:313)
at org.apache.logging.log4j.core.LoggerContext.setConfiguration(LoggerContext.java:631)
at org.apache.logging.log4j.core.LoggerContext.reconfigure(LoggerContext.java:713)
at org.apache.logging.log4j.core.LoggerContext.reconfigure(LoggerContext.java:735)
at org.apache.logging.log4j.core.LoggerContext.start(LoggerContext.java:260)
at org.apache.logging.log4j.core.impl.Log4jContextFactory.getContext(Log4jContextFactory.java:154)
at org.apache.logging.log4j.core.impl.Log4jContextFactory.getContext(Log4jContextFactory.java:46)
at org.apache.logging.log4j.LogManager.getContext(LogManager.java:197)
at org.apache.logging.log4j.spi.AbstractLoggerAdapter.getContext(AbstractLoggerAdapter.java:136)
at org.apache.logging.slf4j.Log4jLoggerFactory.getContext(Log4jLoggerFactory.java:58)
at org.apache.logging.log4j.spi.AbstractLoggerAdapter.getLogger(AbstractLoggerAdapter.java:46)
at org.apache.logging.slf4j.Log4jLoggerFactory.getLogger(Log4jLoggerFactory.java:32)
at org.slf4j.LoggerFactory.getLogger(LoggerFactory.java:363)
at org.slf4j.LoggerFactory.getLogger(LoggerFactory.java:388)
at org.apache.jmeter.JMeter.<clinit>(JMeter.java:113)
at java.base/jdk.internal.misc.Unsafe.ensureClassInitialized0(Native Method)
at java.base/jdk.internal.misc.Unsafe.ensureClassInitialized(Unsafe.java:1160)
at java.base/jdk.internal.reflect.MethodHandleAccessorFactory.ensureClassInitialized(MethodHandleAccessorFactory.java:300)
at java.base/jdk.internal.reflect.MethodHandleAccessorFactory.newConstructorAccessor(MethodHandleAccessorFactory.java:103)
at java.base/jdk.internal.reflect.ReflectionFactory.newConstructorAccessor(ReflectionFactory.java:200)
at java.base/java.lang.reflect.Constructor.acquireConstructorAccessor(Constructor.java:549)
at java.base/java.lang.reflect.Constructor.newInstanceWithCaller(Constructor.java:499)
at java.base/java.lang.reflect.Constructor.newInstance(Constructor.java:486)
at org.apache.jmeter.NewDriver.main(NewDriver.java:257)
ERROR StatusConsoleListener Null object returned for File in Appenders.
ERROR StatusConsoleListener Unable to locate appender "jmeter-log" for logger config "root"
_ \_\_\_\_ _ \_**\_ \_ \_ \_\_\_** \_ \_\_ ** \_\_\_** **\_** **\_** \_**_
/ \ | _ \ / \ / \_**| | | | \_**\_| | | \/ | \_\_**|\_ _| \_\_\_\_| _ \
 / _ \ | |_) / _ \| | | |_| | _| _ | | |\/| | _| | | | _| | |\_) |
/ **\_ \| **/ **_ \ |_**| \_ | |**_ | |_| | | | | |\_** | | | |**_| _ <
/_/ \_\_| /_/ \_\_\_**|_| |_|**\_**| \_**/|_| |_|\_\_\_**| |\_| |**\_**|\_| \_\ 5.6.3

Copyright (c) 1999-2024 The Apache Software Foundation

allt hamnar i att att macens / är skrivskyddat :-(
testar senare
