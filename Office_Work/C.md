login as: gstansiusr
Pre-authentication banner message from server:
|
|  W A R N I N G
|
| THE PROGRAMS AND DATA STORED ON THIS SYSTEM ARE LICENSED TO OR ARE THE PROPER
> TY OF GOODS AND SERVICE TAX NETWORK.  THIS IS A PRIVATE COMPUTING SYSTEM FOR
> USE ONLY BY AUTHORIZED USERS.  ANY UNAUTHORIZED ACCESS TO ANY PROGRAM OR DATA
>  ON THIS SYSTEM IS NOT PERMITTED.
|
| BY ACCESSING AND USING THIS SYSTEM YOU ARE CONSENTING TO SYSTEM MONITORING FO
> R LAW ENFORCEMENT AND OTHER PURPOSES. UNAUTHORIZED USE OF THIS SYSTEM MAY SUB
> JECT YOU TO CRIMINAL PROSECUTION AND PENALTIES.
|
End of banner message from server
gstansiusr@30.0.16.99's password:
    +----------------------------------------------------------------------+
    ¦                 • MobaXterm Personal Edition v23.2 •                 ¦
    ¦               (SSH client, X server and network tools)               ¦
    ¦                                                                      ¦
    ¦ ? SSH session to gstansiusr@30.0.16.99                               ¦
    ¦   • Direct SSH      :  ?                                             ¦
    ¦   • SSH compression :  ?                                             ¦
    ¦   • SSH-browser     :  ?                                             ¦
    ¦   • X11-forwarding  :  ?  (disabled or not supported by server)      ¦
    ¦                                                                      ¦
    ¦ ? For more info, ctrl+click on help or visit our website.            ¦
    +----------------------------------------------------------------------+


****************************************************************************************************************************************************************
You have logged in to Goods and Service Tax Network server. By logging in to this server, you are agreeing to comply with the laws of monitoring and management as defined by Good and Service Tax Network and Government of India. If you are not authorized to use this system, please log off immediately.
****************************************************************************************************************************************************************
Last login: Wed Dec 18 14:44:23 2024 from 10.205.56.149

****************************************************************************************************************************************************************
You have logged in to Goods and Service Tax Network server. By logging in to this server, you are agreeing to comply with the laws of monitoring and management as defined by Good and Service Tax Network and Government of India. If you are not authorized to use this system, please log off immediately.
****************************************************************************************************************************************************************
[gstansiusr@stgocpbastion ~]$ oc login -u muktikanta
Authentication required for https://api.np.gst.gov.in:6443 (openshift)
Console URL: https://api.np.gst.gov.in:6443/console
Username: muktikanta
Password:
Login successful.

You have access to 98 projects, the list has been suppressed. You can list all projects with 'oc projects'

Using project "uat-release-1".
[gstansiusr@stgocpbastion ~]$ oc get po |grep reg
reg-api-241-2g6m6                       1/1     Running             0                31m
reg-api-aadhaar-1055-z77t2              1/1     Running             0                31m
reg-api-batch-1056-5lp78                1/1     Running             0                4h39m
reg-api-batch-1056-f96zr                1/1     Running             0                4h39m
reg-api-batch-1056-wptrs                1/1     Running             0                4h39m
registration-nginx-218-7sw2h            2/2     Running             0                7d1h
registration-web-271-gkstm              1/1     Running             0                31m
registration-web-aadhaar-253-s8stl      1/1     Running             0                31m
regtrigger-api-20-6xq98                 1/1     Running             0                10d
stak-registration-16-vp97d              1/1     Running             0                10d
[gstansiusr@stgocpbastion ~]$ oc describe po reg-api-241-2g6m6 | grep Image
    Image:          image-registry.openshift-image-registry.svc:5000/uat-release-1/reg-api:20263.649664
    Image ID:       image-registry.openshift-image-registry.svc:5000/uat-release-1/reg-api@sha256:ef5294b6ffd9855c96a11bd910c87adeef8bd489d298801dbeb8e96b71ae9c86
[gstansiusr@stgocpbastion ~]$ oc get po |grep bol
bolitigation-api-98-m4hkf               1/1     Running             0               10d
bolitigation-web-100-tpd5m              1/1     Running             0               81m
[gstansiusr@stgocpbastion ~]$ oc describe po bolitigation-web-100-tpd5m | grep Image
    Image:          image-registry.openshift-image-registry.svc:5000/uat-release-1/bolitigation-web:2178.649834
    Image ID:       image-registry.openshift-image-registry.svc:5000/uat-release-1/bolitigation-web@sha256:3a7634a8ab0febf0ad4e5174e0ed3590d27cdc112fcae4b43783e32366c504a7
[gstansiusr@stgocpbastion ~]$ oc rsh bolitigation-web-100-tpd5m
sh-4.2$ ls webapps
bolitserv.war
sh-4.2$ curl -l localhost:8180/bolitserv/health
sh-4.2$ cd /opt/logs
sh-4.2$ ls
jws.log
sh-4.2$ cat jws.log
2024-12-18 13:34:22,533 INFO : [org.apache.catalina.startup.Catalina] Cluster RuleSet not found due to [java.lang.ClassNotFoundException: org.apache.catalina.ha.ClusterRuleSet]. Cluster configuration disabled.
2024-12-18 13:34:22,539 INFO : [org.apache.catalina.startup.Catalina] Cluster RuleSet not found due to [java.lang.ClassNotFoundException: org.apache.catalina.ha.ClusterRuleSet]. Cluster configuration disabled.
2024-12-18 13:34:23,223 INFO : [org.apache.catalina.startup.VersionLoggerListener] Server version:        Apache Tomcat/8.0.18
2024-12-18 13:34:23,224 INFO : [org.apache.catalina.startup.VersionLoggerListener] Server built:          Apr 1 2016 16:12:44 UTC
2024-12-18 13:34:23,224 INFO : [org.apache.catalina.startup.VersionLoggerListener] Server number:         8.0.18-61_patch_01.ep7.el7.-patch-01
2024-12-18 13:34:23,224 INFO : [org.apache.catalina.startup.VersionLoggerListener] OS Name:               Linux
2024-12-18 13:34:23,225 INFO : [org.apache.catalina.startup.VersionLoggerListener] OS Version:            4.18.0-477.74.1.el8_8.x86_64
2024-12-18 13:34:23,225 INFO : [org.apache.catalina.startup.VersionLoggerListener] Architecture:          amd64
2024-12-18 13:34:23,225 INFO : [org.apache.catalina.startup.VersionLoggerListener] Java Home:             /opt/jdk1.8.0_101/jre
2024-12-18 13:34:23,225 INFO : [org.apache.catalina.startup.VersionLoggerListener] JVM Version:           1.8.0_101-b13
2024-12-18 13:34:23,225 INFO : [org.apache.catalina.startup.VersionLoggerListener] JVM Vendor:            Oracle Corporation
2024-12-18 13:34:23,225 INFO : [org.apache.catalina.startup.VersionLoggerListener] CATALINA_BASE:         /opt/jws-3.0/tomcat8
2024-12-18 13:34:23,226 INFO : [org.apache.catalina.startup.VersionLoggerListener] CATALINA_HOME:         /opt/jws-3.0/tomcat8
2024-12-18 13:34:23,226 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Djava.util.logging.config.file=/opt/jws-3.0/tomcat8/conf/logging.properties
2024-12-18 13:34:23,226 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Djava.util.logging.manager=org.apache.juli.ClassLoaderLogManager
2024-12-18 13:34:23,226 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Djava.library.path=/opt/jws-3.0/tomcat8/lib
2024-12-18 13:34:23,226 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Djava.library.path=/opt/jws-3.0/tomcat8/lib
2024-12-18 13:34:23,227 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -javaagent:/opt/soft/wily/Agent.jar
2024-12-18 13:34:23,227 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Dcom.wily.introscope.agentProfile=/opt/soft/wily/core/config/IntroscopeAgent.profile
2024-12-18 13:34:23,227 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Dcom.sun.management.jmxremote=true
2024-12-18 13:34:23,227 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Dcom.sun.management.jmxremote.ssl=false
2024-12-18 13:34:23,227 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Dcom.sun.mangement.jmxremote.authenticate=false
2024-12-18 13:34:23,227 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -javaagent:/opt/soft/prometheus/jmx_prometheus_javaagent-0.6.jar=7070:/opt/soft/prometheus/Prometheus.yml
2024-12-18 13:34:23,227 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Xms2048m
2024-12-18 13:34:23,227 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Xmx4608m
2024-12-18 13:34:23,228 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:+UseG1GC
2024-12-18 13:34:23,228 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:+UseStringDeduplication
2024-12-18 13:34:23,228 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:ParallelGCThreads=8
2024-12-18 13:34:23,228 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:ConcGCThreads=2 
2024-12-18 13:34:23,228 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:InitiatingHeapOccupancyPercent=50
2024-12-18 13:34:23,228 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:MaxGCPauseMillis=400
2024-12-18 13:34:23,228 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -verbose:gc
2024-12-18 13:34:23,228 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Xloggc:logs/gc.log20241218133405.log
2024-12-18 13:34:23,229 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:+UseGCLogFileRotation
2024-12-18 13:34:23,229 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:GCLogFileSize=10M
2024-12-18 13:34:23,229 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:NumberOfGCLogFiles=10
2024-12-18 13:34:23,229 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:+PrintGCDetails 
2024-12-18 13:34:23,229 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:+PrintGCDateStamps
2024-12-18 13:34:23,229 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:+PrintGCTimeStamps
2024-12-18 13:34:23,229 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:+UnlockDiagnosticVMOptions
2024-12-18 13:34:23,229 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:MetaspaceSize=128M
2024-12-18 13:34:23,230 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:+PrintTenuringDistribution
2024-12-18 13:34:23,230 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -XX:-PrintGCApplicationStoppedTime
2024-12-18 13:34:23,230 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Djava.security.egd=file:/dev/./urandom
2024-12-18 13:34:23,230 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Djava.endorsed.dirs=/opt/jws-3.0/tomcat8/endorsed
2024-12-18 13:34:23,230 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Dcatalina.base=/opt/jws-3.0/tomcat8
2024-12-18 13:34:23,230 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Dcatalina.home=/opt/jws-3.0/tomcat8
2024-12-18 13:34:23,230 INFO : [org.apache.catalina.startup.VersionLoggerListener] Command line argument: -Djava.io.tmpdir=/opt/jws-3.0/tomcat8/temp
2024-12-18 13:34:23,230 INFO : [org.apache.catalina.core.AprLifecycleListener] Loaded APR based Apache Tomcat Native library 1.1.32 using APR version 1.4.8.
2024-12-18 13:34:23,230 INFO : [org.apache.catalina.core.AprLifecycleListener] APR capabilities: IPv6 [true], sendfile [true], accept filters [false], random [true].
2024-12-18 13:34:23,244 INFO : [org.apache.catalina.core.AprLifecycleListener] OpenSSL successfully initialized (OpenSSL 1.0.1e 11 Feb 2013)
2024-12-18 13:34:23,953 INFO : [org.apache.coyote.http11.Http11Nio2Protocol] Initializing ProtocolHandler ["http-nio2-8180"]
2024-12-18 13:34:24,222 INFO : [org.apache.catalina.startup.Catalina] Initialization processed in 2634 ms
2024-12-18 13:34:24,236 INFO : [org.apache.catalina.core.StandardService] Starting service Catalina
2024-12-18 13:34:24,236 INFO : [org.apache.catalina.core.StandardEngine] Starting Servlet Engine: Apache Tomcat/8.0.18
2024-12-18 13:34:24,282 INFO : [org.apache.catalina.startup.HostConfig] Deploying web application archive /opt/jws-3.0/tomcat8/webapps/bolitserv.war
2024-12-18 13:34:24,336 WARN : [org.apache.tomcat.util.digester.Digester] [SetContextPropertiesRule]{Context} Setting property 'usehttponly' to 'true' did not find a matching property.
2024-12-18 13:34:24,358 ERROR: [org.apache.catalina.startup.ContextConfig] Exception fixing docBase for context [/bolitserv] java.util.zip.ZipException: error in opening zip file
        at java.util.zip.ZipFile.open(Native Method)
        at java.util.zip.ZipFile.<init>(ZipFile.java:219)
        at java.util.zip.ZipFile.<init>(ZipFile.java:149)
        at java.util.jar.JarFile.<init>(JarFile.java:166)
        at java.util.jar.JarFile.<init>(JarFile.java:103)
        at sun.net.www.protocol.jar.URLJarFile.<init>(URLJarFile.java:93)
        at sun.net.www.protocol.jar.URLJarFile.getJarFile(URLJarFile.java:69)
        at sun.net.www.protocol.jar.JarFileFactory.get(JarFileFactory.java:99)
        at sun.net.www.protocol.jar.JarURLConnection.connect(JarURLConnection.java:122)
        at sun.net.www.protocol.jar.JarURLConnection.getJarFile(JarURLConnection.java:89)
        at org.apache.catalina.startup.ExpandWar.validate(ExpandWar.java:176)
        at org.apache.catalina.startup.ContextConfig.fixDocBase(ContextConfig.java:627)
        at org.apache.catalina.startup.ContextConfig.beforeStart(ContextConfig.java:744)
        at org.apache.catalina.startup.ContextConfig.lifecycleEvent(ContextConfig.java:307)
        at org.apache.catalina.util.LifecycleSupport.fireLifecycleEvent(LifecycleSupport.java:117)
        at org.apache.catalina.util.LifecycleBase.fireLifecycleEvent(LifecycleBase.java:90)
        at org.apache.catalina.util.LifecycleBase.setStateInternal(LifecycleBase.java:402)
        at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:147)
        at org.apache.catalina.core.ContainerBase.addChildInternal(ContainerBase.java:725)
        at org.apache.catalina.core.ContainerBase.addChild(ContainerBase.java:701)

2024-12-18 13:34:24,376 ERROR: [org.apache.catalina.core.ContainerBase] ContainerBase.addChild: start:  java.util.zip.ZipException: error in opening zip file
        at java.util.zip.ZipFile.open(Native Method)
        at java.util.zip.ZipFile.<init>(ZipFile.java:219)
        at java.util.zip.ZipFile.<init>(ZipFile.java:149)
        at java.util.jar.JarFile.<init>(JarFile.java:166)
        at java.util.jar.JarFile.<init>(JarFile.java:103)
        at org.apache.catalina.webresources.JarResourceSet.initInternal(JarResourceSet.java:88)
        at org.apache.catalina.util.LifecycleBase.init(LifecycleBase.java:102)
        at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:139)
        at org.apache.catalina.webresources.StandardRoot.startInternal(StandardRoot.java:682)
        at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:150)
        at org.apache.catalina.core.StandardContext.resourcesStart(StandardContext.java:4889)
        at org.apache.catalina.core.StandardContext.startInternal(StandardContext.java:5019)
        at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:150)
        at org.apache.catalina.core.ContainerBase.addChildInternal(ContainerBase.java:725)
        at org.apache.catalina.core.ContainerBase.addChild(ContainerBase.java:701)
        at org.apache.catalina.core.StandardHost.addChild(StandardHost.java:714)
        at org.apache.catalina.startup.HostConfig.deployWAR(HostConfig.java:917)
        at org.apache.catalina.startup.HostConfig$DeployWar.run(HostConfig.java:1701)
        at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
        at java.util.concurrent.FutureTask.run(FutureTask.java:266)
Wrapped by: java.lang.IllegalArgumentException: java.util.zip.ZipException: error in opening zip file
        at org.apache.catalina.webresources.JarResourceSet.initInternal(JarResourceSet.java:96)
        at org.apache.catalina.util.LifecycleBase.init(LifecycleBase.java:102)
        ... 16 common frames omitted
Wrapped by: org.apache.catalina.LifecycleException: Failed to initialize component [org.apache.catalina.webresources.JarResourceSet@47ee4e1b]
        at org.apache.catalina.util.LifecycleBase.init(LifecycleBase.java:106)
        at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:139)
        at org.apache.catalina.webresources.StandardRoot.startInternal(StandardRoot.java:682)
        at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:150)
        ... 13 common frames omitted
Wrapped by: org.apache.catalina.LifecycleException: Failed to start component [org.apache.catalina.webresources.StandardRoot@1c48d173]
        at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:154)
        at org.apache.catalina.core.StandardContext.resourcesStart(StandardContext.java:4889)
        at org.apache.catalina.core.StandardContext.startInternal(StandardContext.java:5019)
        at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:150)
        ... 10 common frames omitted
Wrapped by: org.apache.catalina.LifecycleException: Failed to start component [StandardEngine[Catalina].StandardHost[localhost].StandardContext[/bolitserv]]
        at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:154)
        at org.apache.catalina.core.ContainerBase.addChildInternal(ContainerBase.java:725)
        at org.apache.catalina.core.ContainerBase.addChild(ContainerBase.java:701)
        at org.apache.catalina.core.StandardHost.addChild(StandardHost.java:714)
        at org.apache.catalina.startup.HostConfig.deployWAR(HostConfig.java:917)
        at org.apache.catalina.startup.HostConfig$DeployWar.run(HostConfig.java:1701)
        at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
        at java.util.concurrent.FutureTask.run(FutureTask.java:266)
        at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
        at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
        at java.lang.Thread.run(Thread.java:745)

2024-12-18 13:34:24,377 ERROR: [org.apache.catalina.startup.HostConfig] Error deploying web application archive /opt/jws-3.0/tomcat8/webapps/bolitserv.war java.lang.IllegalStateException: ContainerBase.addChild: start: org.apache.catalina.LifecycleException: Failed to start component [StandardEngine[Catalina].StandardHost[localhost].StandardContext[/bolitserv]]
        at org.apache.catalina.core.ContainerBase.addChildInternal(ContainerBase.java:729)
        at org.apache.catalina.core.ContainerBase.addChild(ContainerBase.java:701)
        at org.apache.catalina.core.StandardHost.addChild(StandardHost.java:714)
        at org.apache.catalina.startup.HostConfig.deployWAR(HostConfig.java:917)
        at org.apache.catalina.startup.HostConfig$DeployWar.run(HostConfig.java:1701)
        at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
        at java.util.concurrent.FutureTask.run(FutureTask.java:266)
        at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
        at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
        at java.lang.Thread.run(Thread.java:745)

2024-12-18 13:34:24,378 INFO : [org.apache.catalina.startup.HostConfig] Deployment of web application archive /opt/jws-3.0/tomcat8/webapps/bolitserv.war has finished in 96 ms
2024-12-18 13:34:24,381 INFO : [org.apache.coyote.http11.Http11Nio2Protocol] Starting ProtocolHandler ["http-nio2-8180"]
2024-12-18 13:34:24,382 INFO : [org.apache.catalina.startup.Catalina] Server startup in 159 ms
sh-4.2$
