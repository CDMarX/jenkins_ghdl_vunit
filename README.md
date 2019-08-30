# README #
# jenkins_ghdl_vunit

### What is this for? ###
***
Docker container able to run Jenkins jobs with VUnit tests using GHDL simulator.
This docker container was built using the jenkins container and adding steps from ghdl/ext:vunit.

### How do I get set up? ###
***
With Docker installed, pull the repo from Docker Hub:
```
$ docker pull cdmarx/jenkins_ghdl_vunit
```

To test vunit/ghdl you should started it as:

**[Linux]**
```
$ docker run -v $PWD/my_vhdl_project:/home/my_vhdl_project -it cdmarx/jenkins_ghdl_vunit /bin/bash
```
**[Windows]**
```
C:\> docker run --rm -v C:\my_vhdl_project:/home/my_vhdl_project -it cdmarx/jenkins_ghdl_vunit /bin/bash
```

Then you can go to your test repo (where the run.py file is) and run:
```
$ python3 run.py --xunit-xml test_output.xml
```

To test the Jenkis service you should start it as:
```
$ docker run -p 8080:8080 -p 50000:50000 cdmarx/jenkins_ghdl_vunit
```

When the container is running, you should be able to access Jenkins on your browser at:

http://localhost:8080/
