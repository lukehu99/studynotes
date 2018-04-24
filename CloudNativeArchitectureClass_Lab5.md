Lab 5 Pushing first Application

CLI: https://github.com/cloudfoundry/cli/releases

$ cf api api.run.pivotal.io
$ cf login

$ cf push
(1) push based on the file manifest.yml
(2) invoke call for specific org, space
(3) create route based on configuration
    host: spring-music-${random-word}
(4) binding route to application
(5) upload files to PCF (zip is exploded)
(6) buildpack, create droplet (runtime component), upload droplet to blobstore
(7) start application 

---------------------
Using manifest file /Users/pivotal/mstine/2015/OReilly/CloudNativeArchitectureClass/day_01/session_02/lab_05/spring-music/manifest.yml (1)

Creating app spring-music in org oreilly-class / space instructor as mstine@pivotal.io...
OK (2)

Creating route spring-music-hippest-shaman.cfapps.io...
OK (3)

Binding spring-music-hippest-shaman.cfapps.io to spring-music...
OK (4)

Uploading spring-music... (5)
Uploading app files from: /Users/pivotal/mstine/2015/OReilly/CloudNativeArchitectureClass/day_01/session_02/lab_05/spring-music/build/libs/spring-music.war
Uploading 569.7K, 90 files
Done uploading
OK

Starting app spring-music in org oreilly-class / space instructor as mstine@pivotal.io... (6)
-----> Downloaded app package (21M)
-----> Java Buildpack Version: v2.6.1 |  https://github.com/cloudfoundry/java-buildpack.git#2d92e70
-----> Downloading Open Jdk JRE 1.8.0_31 from https://download.run.pivotal.io/openjdk/lucid/x86_64/openjdk-1.8.0_31.tar.gz (1.3s)
       Expanding Open Jdk JRE to .java-buildpack/open_jdk_jre (1.2s) (7)
-----> Downloading Spring Auto Reconfiguration 1.7.0_RELEASE from https://download.run.pivotal.io/auto-reconfiguration/auto-reconfiguration-1.7.0_RELEASE.jar (0.1s)
-----> Downloading Tomcat Instance 8.0.18 from https://download.run.pivotal.io/tomcat/tomcat-8.0.18.tar.gz (0.4s)
       Expanding Tomcat to .java-buildpack/tomcat (0.1s) (8)
-----> Downloading Tomcat Lifecycle Support 2.4.0_RELEASE from https://download.run.pivotal.io/tomcat-lifecycle-support/tomcat-lifecycle-support-2.4.0_RELEASE.jar (0.0s)
-----> Downloading Tomcat Logging Support 2.4.0_RELEASE from https://download.run.pivotal.io/tomcat-logging-support/tomcat-logging-support-2.4.0_RELEASE.jar (0.0s)
-----> Downloading Tomcat Access Logging Support 2.4.0_RELEASE from https://download.run.pivotal.io/tomcat-access-logging-support/tomcat-access-logging-support-2.4.0_RELEASE.jar (0.0s)
-----> Uploading droplet (66M) (9)

0 of 1 instances running, 1 starting
1 of 1 instances running

App started


OK

App spring-music was started using this command `JAVA_HOME=$PWD/.java-buildpack/open_jdk_jre JAVA_OPTS="-Djava.io.tmpdir=$TMPDIR -XX:OnOutOfMemoryError=$PWD/.java-buildpack/open_jdk_jre/bin/killjava.sh -Xmx382293K -Xms382293K -XX:MaxMetaspaceSize=64M -XX:MetaspaceSize=64M -Xss995K -Daccess.logging.enabled=false -Dhttp.port=$PORT" $PWD/.java-buildpack/tomcat/bin/catalina.sh run` (10)

Showing health and status for app spring-music in org oreilly-class / space instructor as mstine@pivotal.io... (11)
OK

requested state: started
instances: 1/1
usage: 512M x 1 instances
urls: spring-music-hippest-shaman.cfapps.io
last uploaded: Fri Feb 13 15:43:08 UTC 2015

     state     since                    cpu    memory           disk
#0   running   2015-02-13 09:43:55 AM   0.0%   394.5M of 512M   131.1M of 1G
---------------------
