JAVA
====


* Updating default Java executables with new executables :: 

        # update-alternatives --install <symlink of java executable> <config_name> <newer java binary> <priority>

  **Usage** :

        # update-alternatives --install "/usr/bin/java" "java" "/usr/java/default/bin/java" 3

        # update-alternatives --install "/usr/bin/javac" "javac" "/usr/java/default/bin/javac" 3

        # update-alternatives --install "/usr/bin/javaws" "javaws" "/usr/java/default/bin/javaws" 3

