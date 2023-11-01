# Quick Taskwarrior tutorial

- git clone or download/extract a release tarball
```
git clone git@github.com/GothenburgBitFactory/taskwarrior
cd taskwarrior
cmake -DCMAKE_BUILD_TYPE=release .
make
# Assume ~/bin is in your path... put it where you like
cp src/task ~/bin/
```

- Add a new task, due in four hours
```
task add Build a new foo project:this status:pending due:+4h
```

- Make task /foo/ searches case-insensitive...
```
echo 'search.case.sensitive=no' >> ~/.taskrc
```

- Add a new task that depends on the first one, due at end of month
```
task add Build a new bar depends:1 project:this status:pending due:eom
```

- List the tasks (default in ~/.task/pending.data): `task`

- Detail about task number 1: `task 1`

- Modify the project for task 1, and make it recur daily
```
task modify 1 project:that recur:daily
```

- Get completed tasks matching the string "foo"
```
task completed /foo/
```

- Export tasks as json
```
task export
```

- Delete task number 1
```
task rm 1
```
