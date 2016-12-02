# Golang-Log

This is my Golang log. Write about the way to do and don't do in golang while coding and form experience.

### goroutine duplicate
======
#### Do not !!!

````go
var pc_pool []ProcessWatcherGroup
for _, procg := range pc_pool{
    //in this function, it create many goroutine
		procg.Watch()
}
````

#### Please Do
````go
var pc_pool []ProcessWatcherGroup
for i := 0; i < len(pc_pool); i++{
	pc_pool[i].Watch()
}
````
======

### Like IO Error in Windows
=====
#### Do not !!!

````go
func main(){
  //...
  for{
    //do nothing
  }
}
````

#### Please Do
````go
func main(){
  //...
  for(){
    time.Sleep(time.Duration(n) * time.Second)
  }
}
````
=====
