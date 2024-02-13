# 2024_02_02_HelloCarRcFromScratch

[![image](https://github.com/EloiStree/2024_02_02_HelloCarRcFromScratch/assets/20149493/b52debd0-f691-4a0d-81ef-5b316a43a856)](https://youtu.be/CrI-iCATU2g)

We try to learn how we can use Scratch as an controller for third application like Hello Car RC


- https://youtu.be/CrI-iCATU2g
- https://scratch.mit.edu/cloudmonitor/960534356/
- https://scratch.mit.edu/projects/960534356/
- https://en.scratch-wiki.info/wiki/Cloud_Data

``` python



from scratchclient import ScratchSession

def read_file(file_path):
    try:
        with open(file_path, 'r') as file:
            file_content = file.read()
            return file_content
    except FileNotFoundError:
        return f"Error: File '{file_path}' not found."
    except Exception as e:
        return f"Error: {e}"


password= read_file("password.txt")
name ="EloiStree"

session = ScratchSession(name, password)


# lots of other stuff

print(session.get_studio(34580905).description)
print(session.get_project(960534356).get_comments()[0].content)

print("T0")

connection = session.create_cloud_connection(960534356)


print("T1")

@connection.on("set")
def on_set(variable):
    print(variable.name, variable.value)
    

print("T2")
connection.set_cloud_variable("Test", 42)
print(connection.get_cloud_variable("Test"))

print("End")

```


--------------------

|Teacher |Student|
|-|-|
| [![Teacher](https://github.com/EloiStree/2024_02_02_HelloCarRcFromScratch/assets/20149493/8e5ecdf9-661c-4341-a0d3-68d27b3feea1)](https://scratch.mit.edu/users/EloiStree/) | [![Student](https://github.com/EloiStree/2024_02_02_HelloCarRcFromScratch/assets/20149493/978b26d4-b281-4ce9-8e89-aa19b5d9ee19)](https://scratch.mit.edu/users/eloiscratchstudents/) |
- [EloiStree](https://scratch.mit.edu/users/EloiStree/)
- [EloiScratchStudents](https://scratch.mit.edu/users/eloiscratchstudents/)  


Student account for workshop in real life:  
[eloiscratchstudents](https://scratch.mit.edu/users/eloiscratchstudents/)https://scratch.mit.edu/users/eloiscratchstudents/ 
