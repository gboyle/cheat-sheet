
# Java

### Quickstart Archetype

    mvn archetype:generate \
    -DgroupId=com.mycompany.app \
    -DartifactId=my-app \
    -DarchetypeArtifactId=maven-archetype-quickstart \ 
    -DinteractiveMode=false

Be careful, there should be no spaces after the line continuation chacter \.
Note that on Windows, use ^ instead of \.

[Maven in 5 Minutes](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html)

### CXF Archetype

    mvn archetype:generate \
    -DgroupId=com.mycompany.srv \
    -DartifactId=my-srv \
    -DarchetypeGroupId=org.apache.cxf.archetype \
    -DarchetypeArtifactId=cxf-jaxrs-service \ 
    -DinteractiveMode=false

### CXF Multiparts

[JAX-RS : Support for Multiparts ](http://cxf.apache.org/docs/jax-rs-multiparts.html)

### CXF Debugging Tools

[Debugging Tools](http://cxf.apache.org/docs/debugging-and-logging.html)

### Upload Files

    curl -X POST -F 'key1=value1' -F 'key2=value2' -F 'file1=@file1.txt' -F 'file2=@file2.txt' http://localhost:8080/my/downloads

[POST Form Data with cURL](https://davidwalsh.name/curl-post-file)

### Maven

To clean and compile to war

    mvn clean package
	
To clean, compile to war and install to repository

    mvn clean install

Use -DskipTests with maven to skip tests during build
 
	mvn clean package -DskipTests

### Exceptions

    class MyLibraryException extends Exception {

        private Throwable cause;

        public MyLibraryException(String message, Object... args) {
            super(someformatter(message,args));
            cause=null;
        }

        private MyLibraryException(Throwable throwable, String message) {
            super(message);
            cause=throwable;
        }

        public static MyLibraryException wrap(Throwable throwable, String message, Object... args) {

            if(throwable instanceof MyLibraryException) {
                return (MyLibraryException) throwable;
            }

            return new MyLibraryException(throwable,someformatter(message,args));
        }

        public Throwable getCause() {
            return cause;
        }    
    }

    class MyLibraryClass {

        public foo() throws MyLibraryException {

            try {
                // danger Will Robinson
            } catch (IOException|SQLException e) {
                // don't ignore exceptions
                // don't printStackTrace (it bypasses loggers)
                // don't catch RuntimeException
                // catch specific exceptions if at all possible
                // preserve the inner exceptions (cause and stack trace)
                // wrap exceptions to reduce the list of exceptions propagated to library users
                throw MyLibraryException.wrap(e,"foo failed");
            }
        }

        public bar() throws MyLibraryException {

            try {            
                // for some reason we can't explicitly handle each exception generated here
            } catch (RuntimeException e) {
                // don't handle/wrap RuntimeException                
                throw e;    
            } catch (Exception e) {                
                // wrap all other Exceptions 
                throw MyLibraryException.wrap(e,"foo failed");
            }
        }        
    }

[FindBugs Bug Descriptions](http://findbugs.sourceforge.net/bugDescriptions.html)  
[Best Practices for Exception Handling](http://www.onjava.com/pub/a/onjava/2003/11/19/exceptions.html)  
[Top 20 Java Exception Handling Best Practices](http://howtodoinjava.com/best-practices/java-exception-handling-best-practices/)  
[Exception-Handling Antipatterns Blog](https://community.oracle.com/docs/DOC-983543#antipatterns)  

### Misc

Running an application compiled as a jar file:

	java -classpath someapp-0.1.jar com.example.SomeClass

Running a bare .class file

	blah\
		MyClass.class
	lib\
		some.jar
		
	java -classpath .;some.jar blah.MyClass <args>

What's in a jar file?

	jar tvf someapp-0.1.jar
