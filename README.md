# Test Crestron's CMutex and CEvent classes.

## CEventTest Results

**Program Start**
``` text
Waiting for event to get signaled 
Event signaled 
Waiting for event to get signaled 
```
**Pulsing Test1**
``` text
Event signaled 
Waiting for event to get signaled 
Signaling event Now. Returned 1 
```
**Pulsing Test1**
``` text
Signaling event Now. Returned 1 
Event signaled 
Waiting for event to get signaled 
```
**Pulsing Test1**
``` text
Signaling event Now. Returned 1 
Event signaled 
Waiting for event to get signaled 
```

## CEventCMutex Results

### Just Test1

**Setting Test1 High**
```text
Inside callback for test1 - Try grabbing the mutex 
Inside callback for test1 - Obtained mutex. Now waiting now event which will tell us to release the mutex 
```

**Setting Test1 Low**
```text
Setting the event now which will tell the thread to release the mutex 
Releasing the mutex now 
```

### Just Test2
**Setting Test2 High**
```text
Inside callback for test2 - Try grabbing the mutex 
Inside callback for test2 - Obtained mutex Now waiting now event which will tell us to release the mutex
```
**Setting Test2 Low**
```text
Inside release callback for test2 - Release the mutex 
Exception thrown Index out of Range, line 38 
Releasing the mutex now in callback 2
```


### Test1 High-Test2High-Test2Low-Test1Low

**Setting Test1 High**
```text
Inside callback for test1 - Try grabbing the mutex 
Inside callback for test1 - Obtained mutex. Now waiting now event which will tell us to release the mutex 
```

**Setting Test2 High**
```text
Inside callback for test2 - Try grabbing the mutex 
```
**Setting Test2 Low**
```text
Inside release callback for test2 - Release the mutex 
Exception thrown Index out of Range, line 38 
Releasing the mutex now 
Inside callback for test2 - Obtained mutex Now waiting now event which will tell us to release the mutex
```
**Setting Test1 Low**
```text
Setting the event now which will tell the thread to release the mutex 
Releasing the mutex now in callback 2
```

## Rentry Test

**Pulsing 5 times**
```text
[1581] - Calling Mutex Function with Index 1
[1581] - Entered Mutex with index 1
[1643] - Calling Mutex Function with Index 2
[1691] - Calling Mutex Function with Index 3
[1738] - Calling Mutex Function with Index 4
[1781] - Finished processing index 1
[1782] - Entered Mutex with index 2
[1782] - Calling Mutex Function with Index 5
[1982] - Finished processing index 2
[1982] - Entered Mutex with index 3
[2182] - Finished processing index 3
[2182] - Entered Mutex with index 4
[2382] - Finished processing index 4
[2382] - Entered Mutex with index 5
[2582] - Finished processing index 5
``` 